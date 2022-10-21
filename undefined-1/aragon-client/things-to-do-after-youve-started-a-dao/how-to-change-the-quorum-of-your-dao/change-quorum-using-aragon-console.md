# आरागॉन कंसोल का उपयोग करके कोरम बदलें

{% hint style="info" %}
यह मार्गदर्शिका आपको दिखाएगी कि आरागॉन कंसोल का उपयोग करके पास होने के लिए आपके डीएओ में वोटों के लिए आवश्यक न्यूनतम कोरम (मतदान) को कैसे बदला जाए।
{% endhint %}

अपने डीएओ वेब पते के अंत में /कंसोल जोड़कर अपना डीएओ खोलें। यूआरएल इस तरह दिखेगा:  `https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
उपरोक्त URL में को अपने DAO के नाम से बदलें `<your-dao-name>`&#x20;
{% endhint %}

आपको नीचे जैसा कुछ देखना चाहिए:

<figure><img src="../../../../.gitbook/assets/immagine1.png" alt=""><figcaption></figcaption></figure>

अगला  `Exec`चुनें जो एक कमांड है जिसका उपयोग लेनदेन DAO करने के लिए किया जाता है।

अब आपको नीचे दी गई स्क्रीन देखनी चाहिए। वोटिंग चुनें, क्योंकि आप वोटिंग ऐप में बदलाव करेंगे:

<figure><img src="../../../../.gitbook/assets/immagine2.png" alt=""><figcaption></figcaption></figure>

[गिथब](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol) पर वोटिंग ऐप के स्रोत कोड में आप न्यूनतम स्वीकृत कोरम प्रतिशत को बदलने के लिए एक फ़ंक्शन पा सकते हैं, ठीक वही जो हमें चाहिए:

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

अब हम इस फंक्शन को आरागॉन कंसोल से कॉल करेंगे। हमें कंसोल में कमांड में `changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)` जोड़ना होगा, लेकिन पहले हम `uint64 _minAcceptQuorumPct`  को आपके वांछित न्यूनतम कोरम प्रतिशत से बदल देंगे।

This is expressed as a percentage of `10^18` , so for example `100% = 10^18` and `1% = 10^16`. Say you want a new minimum Quorum of 25%, then you need to add 16 zeroes to 25 coming to `250000000000000000`

इसे 10^18 के प्रतिशत के रूप में व्यक्त किया जाता है, उदाहरण के लिए `100% = 10^18` and `1% = 10^16`। मान लें कि आप 25% का एक नया न्यूनतम कोरम चाहते हैं, तो आपको `250000000000000000`पर आने वाले 25 में 16 शून्य जोड़ना होगा



{% hint style="danger" %}
**चेतावनी**

**आपके डीएओ के भीतर वोटों के लिए आवश्यक समर्थन प्रतिशत से न्यूनतम कोरम प्रतिशत कभी भी अधिक नहीं हो** सकता है! इसलिए सुनिश्चित करें कि आपके डीएओ का आवश्यक समर्थन प्रतिशत 55% या उससे अधिक है। यदि नहीं, तो इस ट्यूटोरियल के लिए आवश्यक समर्थन प्रतिशत से कम प्रतिशत का उपयोग करें (अन्यथा आप बाद में समस्या का सामना करेंगे)।.
{% endhint %}

अब कंसोल में कमांड में `changeMinAcceptQuorumPct(250000000000000000)`जोड़ें:

<figure><img src="../../../../.gitbook/assets/immagine 3.png" alt=""><figcaption></figcaption></figure>

जब आप अब 'एंटर' दबाते हैं, तो आपके वेब3 प्रदाता (अधिकांश उपयोगकर्ताओं के लिए मेटामास्क) में एक लेनदेन आना चाहिए। जाँच करें कि क्या न्यूनतम कोरम प्रतिशत आपके मन में रखी गई बातों से मेल खाता है:

<figure><img src="../../../../.gitbook/assets/immagine4.png" alt=""><figcaption></figcaption></figure>

लेन-देन बनाएँ' पर क्लिक करें और इसे अपने वेब3 प्रदाता के साथ हस्ताक्षर करें।

आप लगभग वहाँ हैं! लेकिन पहले वोटिंग ऐप पर जाएं क्योंकि इस बदलाव ने अपने आप वोट जेनरेट कर दिया है। अब आप (और आपके DAO सदस्यों में से पर्याप्त) को इसे पारित करने के लिए वोट को स्वीकृत करने की आवश्यकता है:

<figure><img src="../../../../.gitbook/assets/immagine5.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
चेतावनी

परिवर्तन केवल तभी लागू किया जा सकता है जब शेष मतदान का समय समाप्त हो जाए। इस उदाहरण के मामले में, शेष समय  है`23H:59M:12S` :point\_up:
{% endhint %}

जब मतदान का समय समाप्त हो जाए तो 'इस वोट को लागू करें' पर क्लिक करें और अपने वेब3 प्रदाता के साथ लेनदेन पर हस्ताक्षर करें:

<figure><img src="../../../../.gitbook/assets/immagine6.png" alt=""><figcaption></figcaption></figure>

एक बार ऐसा करने के बाद न्यूनतम कोरम प्रतिशत को 25% तक समायोजित किया जाना चाहिए था। आप एक नया वोट बनाकर इसकी दोबारा जांच कर सकते हैं। जब आप वोट खोलते हैं, तो न्यूनतम अनुमोदन  `>25%` आवश्यक समायोजित किया जाना चाहिए था।

{% hint style="success" %}
यदि आपने इसे इतना दूर कर दिया है, तो अच्छा किया!! :clap:
{% endhint %}

> <mark style="color:purple;">क्या आपको कोई प्रश्न पूछना है? हमारे प्रवचन मंच पर अपनी टिप्पणियाँ यहाँ छोड़ें\*\*</mark> 👇\*\*

{% embed url="https://support.aragon.org/" %}
