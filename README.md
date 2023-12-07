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

> Add the dependency (Facebook Ads Library) - 
```
dependencies {
          implementation 'com.github.AtikulSoftware:FacebookMetaAds:1.0.0'
  }
```

> Step 1. SplashScreen Code - 
```
//SplashScreen
        final Handler handler = new Handler();
        handler.postDelayed(new Runnable() {
            @Override
            public void run() {
                //Code here
                Intent myIntent = new Intent(SplashScreen.this, Home.class);
                startActivity(myIntent);
                finish();
            }
        },5000);
```

> Step 2. Ads Control - 
```
public static void AdUnit(){
        //facebook=========================================================================
        com.atikulsoftware.metaadslibrary.MetaAds.AdsUnit.INTERSTITIAL = "IMG_16_9_APP_INSTALL#YOUR_PLACEMENT_ID";
        com.atikulsoftware.metaadslibrary.MetaAds.AdsUnit.BANNER = "IMG_16_9_APP_INSTALL#YOUR_PLACEMENT_ID";
    }

```

> Setp 3. SplashScreen.Java Code, Bellow OnCreate Bundle - 
```
 //Quick Ads Load=========================================================
        AdsControl.AdUnit();
        FacebookAds.loadInterstitial(SplashScreen.this);
```
> Step 4. Banner Ads Show, Home.Java, Bellow OnCreate Bundle - 
```
//Facebook ads
FacebookAds.setBanner(findViewById(R.id.layBottomBanner), Home.this);
```

> Step 5. Final Code Iplement, Interstitial Ads - 
```
 //Show Interstitial Ads
new FacebookAds(() -> {
 // Next Action


 }).showInterstitial();
```

## In Cooperation

* **Md. Hasan Mahmud** - *Mobile Application Developer* - *Free Library*
