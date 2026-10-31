MMG Android WebView Template

ما الذي يفعله هذا القالب؟
- يحول صفحة HTML محلية إلى تطبيق Android بسيط باستخدام WebView.
- يضم إعداد بناء APK تجريبي (Debug) عبر GitHub Actions.
- لا يحتاج إلى سيرفر خاص تديره أنت، لكن البناء يتم على خوادم GitHub ويتطلب الإنترنت وحساب GitHub.

الخطوات:
1) أنشئ مستودع GitHub جديدًا وارفع كل محتويات هذا المجلد إليه.
2) افتح تبويب Actions في المستودع.
3) اختر "Build Android APK" ثم اضغط Run workflow.
4) بعد انتهاء البناء افتح نتيجة التشغيل، ثم نزّل Artifact باسم mmg-debug-apk.
5) فك ضغط الملف الناتج لتحصل على app-debug.apk.

لاختبار مشروع HTML الخاص بك:
1) من MMG BUILDER افتح المشروع واضغط "تنزيل HTML".
2) سمّ الملف index.html إذا لم يكن اسمه كذلك.
3) استبدل الملف:
   app/src/main/assets/index.html
   بملف مشروعك.
4) ارفع التعديل إلى GitHub وأعد تشغيل Workflow.

ملاحظات مهمة:
- هذا قالب اختبار أولي، وليس دمجًا مباشرًا لزر Build داخل واجهة MMG BUILDER.
- APK الناتج Debug للتجربة والتثبيت الشخصي، وليس إصدارًا منشورًا على المتجر.
- ملفات CSS وJavaScript التي تضعها في محرر MMG BUILDER تُدمج في تنزيل HTML بحسب كود الإصدار الحالي.
- اسم الحزمة وإصدار التطبيق يتم تعديلها من app/build.gradle.kts.
- تغيير اسم التطبيق يتم من android:label في AndroidManifest.xml.
- لتطبيقات تحتاج إنترنت أضف صلاحية INTERNET إلى AndroidManifest.xml، ولا تضفها إلا عند الحاجة.
