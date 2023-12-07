<br/>
<p align="center">
  <a href="https://github.com/AppBondTech/Easy_InAppUpdate">
    <img src="https://mdhasanmahmud.000webhostapp.com/inappupdate/appbondtech.jpg" alt="Logo" width="150" height="150">
  </a>

  <h3 align="center">Master Juba/Funny Video Project -  Facebook Ads Implement</h3>

  <p align="center">
    Best Easy Way for Facebook Ads Implement
    <br/>
    <br/>
    <a href="https://youtu.be/yvtoXlZvuvk"><strong> For Details Video Tutorial »</strong></a>
    <br/>
    <br/>
	  
## Getting Started

> Step 1. Make Sure Add Internet and Ads Permissiton in Manifests - 
```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
<uses-permission android:name="com.google.android.gms.permission.AD_ID" />
```

> Step 2. Add the dependency - 
```
implementation 'com.google.android.ump:user-messaging-platform:2.1.0'
```

> Step 3. Above On Create Bundle is where we declare various variables - 
```
private ConsentInformation consentInformation;
private final AtomicBoolean isMobileAdsInitializeCalled = new AtomicBoolean(false);
```

> Setp 4. Anywhere in the On Create Bundle - 
```
  //Create GDPR_Message (1st part)------------------------------------------------------ 
       
         ConsentRequestParameters params = new ConsentRequestParameters
                .Builder()
                .setTagForUnderAgeOfConsent(false)
                .build();

  consentInformation = UserMessagingPlatform.getConsentInformation(this);
consentInformation.requestConsentInfoUpdate(
     this,
  params,
 (ConsentInformation.OnConsentInfoUpdateSuccessListener) () -> {
 UserMessagingPlatform.loadAndShowConsentFormIfRequired(
   this,
       (ConsentForm.OnConsentFormDismissedListener) loadAndShowError -> {
if (loadAndShowError != null) {
 // Consent gathering failed.
 Log.w(TAG, String.format("%s: %s",
 loadAndShowError.getErrorCode(),
 loadAndShowError.getMessage()));
  }

      // Consent has been gathered.
        if (consentInformation.canRequestAds()) {
              initializeMobileAdsSdk();
           }
      }
      );
   },
   (ConsentInformation.OnConsentInfoUpdateFailureListener) requestConsentError -> {

 // Consent gathering failed.
          Log.w(TAG, String.format("%s: %s",
              requestConsentError.getErrorCode(),
              requestConsentError.getMessage()));
                    
  });

        
        if (consentInformation.canRequestAds()) {
            initializeMobileAdsSdk();
        }

```
> Step 5. Just below the last second bracket - 
```
//Create GDPR_Message (2nd part)------------------------------------------------------ 
 private void initializeMobileAdsSdk() {
    if (isMobileAdsInitializeCalled.getAndSet(true)) {
      return;
    }
}
```

## In Cooperation

* **Md. Hasan Mahmud** - *Mobile Application Developer* - *Free Library*
