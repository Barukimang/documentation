# कानूनी एकीकरण के लिए एक नया टोकन जोड़ना

{% hint style="info" %}
इस खंड में, हम दिखाते हैं कि कैसे **आरागॉन एक कानूनी इकाई जैसे सीरीज डेलावेयर एलएलसी के साथ बातचीत कर सकता है**। हमारे उदाहरण में आरागॉन डीएओ ग्नोसिस सेफ और **ईवीएम-सीआरआईएसपीआर** का भी लाभ उठाता है, यह दिखाने के लिए कि मौजूदा डीएओ कानूनी संस्थाओं तक कैसे पहुंच प्राप्त कर सकता है।
{% endhint %}

## परिचय

कानूनी आवरण एक चुनौतीपूर्ण विषय है, और स्पष्टता के लिए यहां लेखक वकील या कानूनी सलाह नहीं दे रहा है ... एक अनिवार्य रूप से उपयोगी प्रक्रिया के रूप में सेवा करने के लिए, और आलोचना के लिए एक प्रारंभिक बिंदु के रूप में...

## शुरू





[यहां](https://client.aragon.org/#/) से अपना डीएओ बनाएं। इस उदाहरण के लिए, मैंने एक [आरागॉन प्रतिष्ठा डीएओ बनाया है](../how-to-create-a-dao-using-aragon-client/page-1.md)\


![Basic DAO with a reputation DAO - used because these tokens should be non-transferable](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.35.12 PM.png>)

## मिंट योर टोकन

फिर EVM CRISPR पर जाएं जहां आप एक नया टोकन बनाने के लिए कुछ कोड डाल सकते हैं।&#x20;



* अपना वॉलेट कनेक्ट करें&#x20;
* कंसोल साफ़ करें&#x20;
* इन आदेशों को कॉपी और पेस्ट करें&#x20;



```
connect your-dao-here token-manager voting 
new token "Test Token" TEST token-manager:new
install token-manager:new token:TEST true 0
grant voting token-manager:new MINT_ROLE voting
grant voting token-manager:new BURN_ROLE voting
exec token-manager:new mint @me 100e18
```

* फॉरवर्ड कमांड पर क्लिक करें और अपने वॉलेट पर लेनदेन पर हस्ताक्षर करें
* &#x20;लेनदेन पर हस्ताक्षर करें लेन-देन की पुष्टि होने के बाद, गो वोट पर क्लिक करें और अपने डीएओ पर वोट करें

![EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.10.14 PM.png>)

![Vote on your EVM CRISPR transaction](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.32.09 PM.png>)

अब जब आपने अपने नए टोकन बना लिए हैं तो आप उन्हें अपनी टोकन सूची में देख सकते हैं।\


![This is our DAO](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.44 PM.png>)

## आपके लिए कानूनी आवरण आरागॉन डीएओ

अब [ग्नोसिस](https://gnosis-safe.io/) पर जहां हम बिंदुओं को जोड़ने जा रहे हैं।

* एक ग्नोसिस सुरक्षित तिजोरी बनाएं (अधिक सहायता के लिए [यहां](https://help.gnosis-safe.io/en/articles/3876461-creating-a-safe-on-a-web-browser) जाएं) और लेन-देन पर हस्ताक्षर करने के लिए अपनी तिजोरी में कुछ धनराशि जमा करें।&#x20;
* ओटोको ऐप लोड करें&#x20;
* अपनी कंपनी को नाम दें और डेलावेयर, यूएनए और व्योमिंग डीएओ के बीच चयन करें।&#x20;
* भुगतान स्वीकृत(अप्रूव पैमन्ट) करें और कंपनी को सक्रिय(ऐक्टवैट) करें&#x20;

&#x20;मुख्य चरण नीचे दी गई छवियों में दिखाए गए हैं।

![नोसिस में एक तिजोरी बनाएं](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.21 PM.png>) ![ओटोको ऐप लोड करें](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.31 PM.png>) ![अपनी कंपनी का नाम दें और डेलावेयर, यूएनए और व्योमिंग डीएओ के बीच चुनें](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.46 PM.png>) ![अपने स्वाद और टकसाल चुनें!
](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.58 PM (1).png>)

यदि आपको "आपका एंटिटी स्मार्ट कॉन्ट्रैक्ट वॉलेट नहीं है" जैसा संदेश दिखाई देता है, तो "एसेट वॉलेट" पेज पर जाएं और एक मालिक (_वॉलेट एड्रेस या ग्नोसिस सेफ एड्रेस_) जोड़ें।

![](<../../../.gitbook/assets/Schermata 2022-06-07 alle 14.50.29.png>)

फिर _टोकन पेज_ पर जाएं और अपने टोकन के पते को कॉपी और पेस्ट करें (आप इसे अपने डीएओ में [संगठन](../explore-template-dao/system-setting/organization-setting.md) पेज पर पा सकते हैं)।

![Transfer the tokens from your DAO to your Otoco LLC](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.31 PM.png>)

अब आपके पास एक डेलावेयर एलएलसी है जिसमें आरागॉन टकसाल टोकन है!

![](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.15.49 PM.png>)





> <mark style="color:purple;">क्या आपको कोई प्रश्न पूछना है? हमारे प्रवचन मंच पर अपनी टिप्पणियाँ यहाँ छोड़ें</mark> **👇**

{% embed url="https://support.aragon.org/t/aragon-client-legal-wrappers/173" %}
