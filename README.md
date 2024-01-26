# Chose SIM Popup


#### কল বাটনে ক্লিক করলে, পপ-আপ সো হবে।

#### এইটা করার জন্য special permission নিতে হবে । 

## ১। with special permission
### Manifest এ এই permission নিবেন । 

```
<uses-feature
        android:name="android.hardware.telephony"
        android:required="false" />
<uses-permission android:name="android.permission.CALL_PHONE"/>
```
    
### তারপর button এর onClick এর মধ্যে এইভাবে কোড লিখবেন । 

```
String number = "123456789";
Intent callIntent = new Intent(Intent.ACTION_CALL);
callIntent.setData(Uri.parse("tel:"+number));
startActivity(callIntent);
```
            
### নোটঃ অবশ্যই আগে CALL_PHONE এর runtime permission allow করতে হবে । 


## ২। without any permisssion: (recommended)

```
String phoneNumber = "1234567890";
Intent intent = new Intent(Intent.ACTION_DIAL);
intent.setData(Uri.parse("tel:" + phoneNumber));
startActivity(intent);
```

