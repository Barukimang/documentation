# EVMcrispr का उपयोग करके कोरम बदलें

{% hint style="info" %}
यह मार्गदर्शिका आपको बताएगी कि [EVMcrispr](https://evm-crispr.blossom.software/#/) का उपयोग करके आपके DAO में वोटों के लिए आवश्यक न्यूनतम कोरम (मतदान) को कैसे बदला जाए।

EVMcrispr एक शक्तिशाली उपकरण है जो आरागॉन डीएओ के साथ बातचीत करने के लिए एक जावास्क्रिप्ट पुस्तकालय(लाइब्रेरी) के साथ एक डोमेन-विशिष्ट भाषा को जोड़ता है।
{% endhint %}

सबसे पहले [यहां](https://evm-crispr.blossom.software/#/) EVMcrispr को ओपन करें और 'Open Terminal' पर क्लिक करें। अब, यह स्क्रीन दिखाई देनी चाहिए:

<figure><img src="../../../../.gitbook/assets/crisper1.png" alt=""><figcaption></figcaption></figure>

अगला टर्मिनल में सभी टेक्स्ट हटाएं:

<figure><img src="../../../../.gitbook/assets/crisper2.png" alt=""><figcaption></figcaption></figure>

अपने वेब3 प्रदाता (अधिकांश उपयोगकर्ताओं के लिए मेटामास्क) से जुड़ने के लिए 'कनेक्ट' पर क्लिक करें।

{% hint style="danger" %}
**चेतावनी**

सुनिश्चित करें कि आप एक खाते को EVMcrispr से जोड़ते हैं, जिसके पास आपके DAO पर हस्ताक्षर करने की अनुमति भी है।
{% endhint %}



अब हम न्यूनतम कोरम प्रतिशत को बदलने के लिए कमांड लिखने जा रहे हैं।&#x20;

अपने डीएओ के लिए न्यूनतम कोरम प्रतिशत बदलने के लिए आपको अपने डीएओ से `connect <dao-name-or-address` के साथ कनेक्ट करना होगा। इसके बाद हम`token-manager voting` जोड़ते हैं क्योंकि `token-manager`र ऐप में`CREATE_VOTES_ROLE`की आवश्यकता होती है, जिससे हम जिस ऐप के साथ इंटरैक्ट करेंगे, उसे वोट करने के लिए कार्रवाई को आगे बढ़ाया जा सके। हमारे पास अब तक यही है:

```
connect <dao-name-or-address> token-manager voting
```

अब हम EVMcrispr टर्मिनल के लिए दूसरी कमांड लाइन लिखेंगे। जोड़ने के लिए सबसे पहले निष्पादन है जो एक कमांड है जिसका उपयोग लेनदेन डीएओ करने के लिए किया जाता है। इसके बाद हम उस ऐप को वोटिंग जोड़ते हैं जिससे हम बातचीत करेंगे। हमारे पास अब तक यही है:

```
connect <dao-name-or-address> token-manager voting
exec voting
```

हालांकि हम तैयार नहीं हैं। जब हम गीथूब पर वोटिंग ऐप के स्रोत कोड में देखते हैं तो हम न्यूनतम स्वीकृत कोरम प्रतिशत को बदलने के लिए एक फ़ंक्शन पा सकते हैं, यह वही है जो हमें चाहिए:

```solidity
function changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)
    external
    authP(MODIFY_QUORUM_ROLE, arr(uint256(_minAcceptQuorumPct), uint256(minAcceptQuorumPct)))
{
    require(_minAcceptQuorumPct <= supportRequiredPct, ERROR_CHANGE_QUORUM_PCTS);
    minAcceptQuorumPct = _minAcceptQuorumPct;

    emit ChangeMinQuorum(_minAcceptQuorumPct);
}
```



अब हम इस फ़ंक्शन को टर्मिनल के लिए कॉल करने के लिए कमांड में जोड़ देंगे। हमें `changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)` जोड़ना होगा, लेकिन पहले हम uint64 `uint64 _minAcceptQuorumPct` को आपके वांछित न्यूनतम कोरम प्रतिशत से बदल देंगे।

&#x20;इसे 10^18 के प्रतिशत के रूप में व्यक्त किया जाता है, उदाहरण के लिए `100% = 10^18` and `1% = 10^16`.। मान लें कि आप 25% का एक नया न्यूनतम कोरम चाहते हैं, तो आपको `250000000000000000` पर आने वाले 25 में 16 शून्य जोड़ना होगा

{% hint style="danger" %}
**चेतावनी**&#x20;

आपके डीएओ के भीतर वोटों के लिए आवश्यक समर्थन प्रतिशत से न्यूनतम कोरम प्रतिशत कभी भी अधिक नहीं हो सकता है! इसलिए सुनिश्चित करें कि आपके डीएओ का आवश्यक समर्थन प्रतिशत 55% या उससे अधिक है। यदि नहीं, तो इस ट्यूटोरियल के लिए आवश्यक समर्थन प्रतिशत से कम प्रतिशत का उपयोग करें (अन्यथा आप बाद में समस्या का सामना करेंगे)।
{% endhint %}



अब टर्मिनल के कमांड में `changeMinAcceptQuorumPct 250000000000000000` जोड़ें:

```
connect <dao-name-or-address> token-manager voting
exec voting changeMinAcceptQuorumPct 250000000000000000
```

आदेश तैयार हैं! उन्हें टर्मिनल में कॉपी/पेस्ट करें और 'फॉरवर्ड ...' बटन पर क्लिक करें:

<figure><img src="../../../../.gitbook/assets/crisper3.png" alt=""><figcaption></figcaption></figure>

अपने Web3 प्रदाता से लेन-देन पर हस्ताक्षर करें और इसे अब सफलतापूर्वक निष्पादित किया जाना चाहिए।

{% hint style="danger" %}
चेतावनी

इस त्रुटि के मामले में अपने डीएओ नाम के मामले में अपने डीएओ पते का उपयोग करें: `Error: ENS <dao-name>.aragonid.eth` रिंकीबी में नहीं मिला, कृपया इसके बजाय DAO का पता दें।
{% endhint %}

हम लगभग तैयार हैं लेकिन पहले अपना डीएओ वेब ब्राउज़र में खोलें। यूआरएल होना चाहिए:&#x20;

`https://client.aragon.org/#/<dao-name-or-address>`

इसके बाद वोटिंग ऐप पर जाएं क्योंकि इस बदलाव ने अपने आप वोट जेनरेट कर दिया है। अब आप (और आपके DAO सदस्यों में से पर्याप्त) को इसे पारित करने के लिए वोट को स्वीकृत करने की आवश्यकता है:

<figure><img src="../../../../.gitbook/assets/crisper4.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
चेतावनी

परिवर्तन केवल तभी लागू किया जा सकता है जब शेष मतदान का समय समाप्त हो जाए। इस उदाहरण के मामले में,`Time remaining` is `23H:59M:12S` :point\_up:
{% endhint %}

जब मतदान का समय समाप्त हो जाए तो 'इस वोट को लागू(इनैक्ट) करें' पर क्लिक करें और अपने वेब3 प्रदाता के साथ लेनदेन पर हस्ताक्षर करें:

<figure><img src="../../../../.gitbook/assets/crisper5.png" alt=""><figcaption></figcaption></figure>



एक बार ऐसा करने के बाद न्यूनतम कोरम प्रतिशत को 25% तक समायोजित किया जाना चाहिए था। आप एक नया वोट बनाकर इसकी दोबारा जांच कर सकते हैं। जब आप वोट खोलते हैं, तो न्यूनतम अनुमोदन को समायोजित किया जाना चाहिए था `>25% needed`.

{% hint style="success" %}
यदि आपने इसे इतना दूर कर दिया है, तो अच्छा किया! :clap:
{% endhint %}



> <mark style="color:purple;">क्या आपको कोई प्रश्न पूछना है? हमारे प्रवचन मंच पर अपनी टिप्पणियाँ यहाँ छोड़ें</mark> <mark style="color:purple;"></mark><mark style="color:purple;">****</mark>** 👇**

{% embed url="https://support.aragon.org/" %}
