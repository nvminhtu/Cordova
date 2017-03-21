# CORDOVA - STEP by STEP
* Cordova dùng để build hybrid App.
* Bạn sử dụng code frontend của bạn (HTML, CSS, Javascript) kết hợp với Cordova để build ứng dụng Cross platform (Android, iOS, Window Phone,....).
* Các Javascript framework như Ionic, Ionic 2.....sử dụng Cordova để build ứng dụng sang mobile (android, ios,...)
* Có nhiều Stack kết hợp với Cordova, Ví dụ như:
HTML, CSS, Javascript + Cordova
HTML, CSS, Javascript Jquery + Cordova,
....
Bên cạnh đó có thể kết hợp backend để làm Restful cho ứng dụng của bạn: Wordpress, Laravel Framework, NodeJS,....
* Thời gian thực hành: 1 giờ.

### CORDOVA COMMAND
* Trước khi cài Cordova, bạn cần cài [NodeJS].
* Bạn vào website chính của [Cordova] để coi cách cài đặt

* Cài Cordova
```sh
npm install -g cordova.
```

* Tạo 1 project sử dụng Cordova
```sh
cordova create <path>
```

* Add platform (Android, IOS) - Bước này là cần thiết vì chúng ta muốn build cho nền tảng nào thì add nền tảng đó vô.
```sh
cordova platform add <platform name>
```

Ví dụ Android
```sh
cordova platform add android
```

* Sau khi chúng ta code - source đã ok, chúng ta build app.

Ví dụ build app Android (Debug file)
```sh
cordova build android
```
Sau khi chạy lệnh trên chúng ta sẽ có 1 file android-debug.apk nằm trong
platforms/android/build/outputs/apk


Ví dụ build app Android bản release
```sh
cordova build --release android
```
Sau khi chạy lệnh trên chúng ta sẽ có 1 file unsigned-release-android.apk nằm trong
platforms/android/build/outputs/apk


* Để chạy thử trên máy ảo/máy thật chúng ta dùng lệnh sau:
```sh
cordova run android
```
Phần cấu hình cho máy ảo và máy thật sẽ cập nhật thêm sau tại đây.

### BUILD APP và RELEASE
* Sau khi build app release xong chúng ta cần jarsingned - add keystore cho nó và zipalign

### Đối với Windows
* Tạo Keystore:
bạn vào đường dẫn sau  "C:\Program Files\Java\jre1.8.0_65\bin"
(jre1.8.0_65 là thư mục cùng cấp nơi bạn đã cài Java SDK).
Sau đó ở Command Line (có thể xài Windows Prompt hoặc Windows Powershell): bạn gõ command như sau:
```sh
keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
```
Trong đó
'my-release-key.keystore' là tên file keystore của bạn sẽ tạo.
'alias_name' là tên của keystore
Sau đó nó yêu cầu nhập thông tin như (Họ Tên, Công ty,...) và nhập password cho keystore này.

* Lưu ý: mỗi app có 1 keystore cho nó dùng để upload và cập nhật app sau này, vì thế bạn cần nhớ password và lưu trữ file cẩn thận.
Nếu mất keystore bạn ko thể cập nhật app đó được nữa.

Có thể tham khảo thêm thông số tại đây [Keystore]

* Jarsigner cho app của bạn:

* Zipalign - add keyst

**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen.
[NodeJS]: <https://nodejs.org/en/>
[Cordova]: <https://cordova.apache.org/>
[Keystore]: <https://www.digitalocean.com/community/tutorials/java-keytool-essentials-working-with-java-keystores>
