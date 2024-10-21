# rn-honeywell-barcode-scanner

This module is fork of react-native-honeywell-scanner-v2.
There is only one reason for this fork,

To solve the following issue by updating the deprecated statements, and then pushing it to npm.
All the work(s) belong(s) to the original repo(s) developer(s).

Best Regards,
Onur

## Getting started

`$ npm install rn-honeywell-barcode-scanner --save`

## Usage
```javascript
import HoneywellScanner from 'rn-honeywell-barcode-scanner';

...

useEffect(() => {
        if( HoneywellScanner.isCompatible ) {
            HoneywellScanner.startReader().then((claimed) => {
                console.log(claimed ? 'Barcode reader is claimed' : 'Barcode reader is busy');
                HoneywellScanner.onBarcodeReadSuccess(event => {
                    console.log('Received data', event.data);
                });

            });


            return(
                () => {
                    HoneywellScanner.stopReader().then(() => {
                        console.log("Freedom!!");
                        HoneywellScanner.offBarcodeReadSuccess();
                    });
                }
            )
        }
    }, []);
```
