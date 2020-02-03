# Dynamsoft JavaScript Barcode SDK for Web  
![Dynamsoft JavaScript Barcode SDK](https://www.dynamsoft.com/blog/wpcontent/uploads/2018/12/blog_dbr6.4.1db06493aba126f0c7f177687cf56a9038dd655a1fd2d4374ab571ce738111858.png)  

[Dynamsoft BarcodeReader SDK for Web](https://www.dynamsoft.com/Products/barcode-recognition-javascript.aspx) is a JavaScript API for barcode scanning based on the **WebAssembly** technology. It supports real-time localization and decoding of various barcode types. The library is capable of scanning barcodes from static images as well as directly from live video streams. It also supports reading multiple barcodes at once.  

Also see [Dynamsoft JavaScript Barcode SDK for Node](https://github.com/dynamsoft-dbr/node-javascript-barcode).  

## Quick Usage(#quick-usage)
### Web
```
<!DOCTYPE html>
<html>
<body>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-javascript-barcode@7.3.0-v0/dist/dbr.js" data-productKeys="PRODUCT-KEYS"></script>
    <script>
        let scanner = null;
        (async()=>{
            scanner = await Dynamsoft.BarcodeScanner.createInstance();
            scanner.onFrameRead = results => {console.log(results);};
            scanner.onUnduplicatedRead = (txt, result) => {alert(txt);};
            await scanner.show();
        })();
    </script>
</body>
</html>
``` 

## Table of Content
- Quick Usage
- Features
- Live Demo
- Getting Started: HelloWorld
- Taking a closer look
    - Initializing
    - Configuring Scanner Settings
    - Customizing the UI
- Advanced Usage
    - Print out log for better debugging
    - Show found barcodes
    - Read a specific area/region
- Self-hosted Deployment
- Changelog
- How to Upgrade
- API Documentation
- License Activation
- License Agreement
- Contact Us

## Feature

- Supported Symbologies:  
1D barcode: **Code 39**, **Code 128**, **Code 93**, **Codabar**, **Interleaved 2 of 5 (ITF)**, **EAN-13**, **EAN-8**, **UPC-A**, **UPC-E**, **Industrial 2 of 5** (Code 2 of 5 Industry, Standard 2 of 5, Code 2 of 5), **Code 39 Extended**.  
2D barcode: **PDF417**, **QR**, **DataMatrix**, **Aztec**, and **MaxiCode**.  
GS1 Databar: **Omnidirectional**, **Truncated**, **Stacked**, **Stacked Omnidirectional**, **Expanded**, **Expanded Stacked** and **Limited**.  
Patch Code  
GS1 Composite Code  
Postal Code: **USPS Intelligent Mail**, **PostNet**, **Planet**, **Australian Post**, **UK Royal Mail (RM4SCC)**.  

- Supported Data Sources: **Blob**, **HTMLImageElement**, **HTMLVideoElement**, and **URL**, etc.  

- Browser Compatibility:
    - Unlike normal server-based applications, this library requires some advanced features which fortunately are supported by all mainstream modern browsers. These advanced features are listed below:
        - MediaDevices/getUserMedia  
          Required only for in-browser video streaming. If a browser doesn't have this API the Single Frame Mode is used automatically. If the API exists but doesn't work correctly, Single Frame Mode can be used as an alternative.  
        - WebAssembly, Blob, URL/createObjectURL, Web Workers  
          These four features are required for the library to work.
     - Combining the requirements above results in the following table of supported browsers.  
     
    **NOTE**: Apart from the browsers, the operating systems running on the target devices may also impose some limitations of their own that could restrict the use of the library. Therefore, the following table serves as a rough estimation instead of an accurate guideline. Browser compatibility ultimately depends on whether the browser on that particular operating system supports the features listed above.  
    
    Browser Name | Version
    :-: | :-:
    Chrome | v57+ (v59+ on Android/iOS<sup>1</sup>)
    Firefox | v52+ (v55+ on Android/iOS<sup>1</sup>)
    Edge<sup>2</sup> | v16+
    Safari<sup>3</sup> | v11+
