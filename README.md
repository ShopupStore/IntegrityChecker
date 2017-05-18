# IntegrityChecker
Sub Resource Integrity Check for Images

Subresource Integrity (SRI) is a security feature that enables browsers to verify that files they fetch are delivered without unexpected manipulation. Currently the original specification is limited to JavaScript and CSS. This is an experimantal JS library to bring SRI support for images. Currently this library only supports sha256 as the data-hash. For SRI to work content server must support CORS.

**Example**

 Markup
 
` <img data-src="https://cdn.example.com/1.jpg" data-hash="496aa8990b87f584dffc43e5953d38abcbc30a2edab131fd304fec43d6d9b289" data-fallback="" class="image">
`  

Include Script

    <script src="/path/integrity-checker-combined.min.js"></script>
    <script type="text/javascript>
     integrityChecker('.image', function (image) {
            console.log('check failed')
            image.classList.add('fallback')
        });
    </script>


**Fallback**

If Integrity check fails you can use the **data-fallback** attribute to load a fallback image from your server

**Callback**

integrityChecker accepts an optional callback  with the Image element as argument. the callback function is called when ever there is an Integrity fail. 

