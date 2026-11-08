# গতি স্টুডিও (Gati Studio) — Android প্রজেক্ট

Capacitor ৮ দিয়ে তৈরি। অ্যাপের কোড `www/index.html`-এ।

## পথ ১: GitHub দিয়ে APK (কম্পিউটারে কিছু ইনস্টল লাগে না)
1. github.com-এ নতুন repository খুলুন।
2. এই ZIP-এর সব ফাইল ও ফোল্ডার (`.github`, `android`, `www`, `package.json`, `package-lock.json`, `capacitor.config.json`, `.gitignore`) repository-তে আপলোড করুন। `.github` ফোল্ডার বাদ গেলে বিল্ড চলবে না।
3. Actions ট্যাবে `Build APK` চলবে (৫–১০ মিনিট)।
4. শেষ হলে ওই রানের Artifacts থেকে `gati-studio-apk` নামান, ভেতরে `app-debug.apk`।
5. ফোনে APK ইনস্টল করুন (অজানা উৎস থেকে ইনস্টলের অনুমতি দিতে হবে)।

## পথ ২: Android Studio দিয়ে
```
npm install
npx cap sync android
npx cap open android
```
Android Studio-তে Build > Build APK(s)। JDK 21 লাগবে।

## অ্যাপের কোড বদলালে
`www/index.html` বদলে `npx cap sync android` চালান, তারপর আবার বিল্ড করুন।

## জানা সীমা
- এটা debug APK। Play Store-এ দিতে হলে signed release বিল্ড লাগবে।
- ফন্ট (Hind Siliguri ইত্যাদি) ইন্টারনেট থেকে আসে। অফলাইনে ফোনের নিজস্ব বাংলা ফন্ট দেখাবে। অফলাইন চাইলে ফন্ট ফাইল `www/` ফোল্ডারে রেখে `@font-face` দিয়ে যোগ করতে হবে।
- GIF/PNG/ভিডিও এক্সপোর্ট ফাইল ক্যাশে লিখে শেয়ার শিট খোলে, সেখান থেকে Files/Drive-এ সেভ করুন।
