# Dynamsoft JavaScript Barcode SDK for Web  
![Dynamsoft JavaScript Barcode SDK](https://www.dynamsoft.com/blog/wpcontent/uploads/2018/12/blog_dbr6.4.1db06493aba126f0c7f177687cf56a9038dd655a1fd2d4374ab571ce738111858.png)  

[Dynamsoft BarcodeReader SDK for Web](https://www.dynamsoft.com/Products/barcode-recognition-javascript.aspx) is a JavaScript API for barcode scanning based on the **WebAssembly** technology. It supports real-time localization and decoding of various barcode types. The library is capable of scanning barcodes from static images as well as directly from live video streams. It also supports reading multiple barcodes at once.  

Also see [Dynamsoft JavaScript Barcode SDK for Node](https://github.com/dynamsoft-dbr/node-javascript-barcode).  

## Quick Usage
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
