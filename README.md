🕹️ Pixel Study Hall · قاعة الدراسة بيكسل
العربية | English

العربية
مساحة ويب ثنائية الأبعاد بنمط البيكسل آرت للدراسة والعمل مع الأصدقاء عن بعد. تدخل بشخصيتك، تجلس على مكتب بجانب زملائك، وتسمع أصواتهم كأنهم بجوارك.

المميزات
🎧 صوت مكاني (Spatial Audio): كلما اقتربت من صديق علا صوته، وكلما ابتعدت خفت. ويتجه الصوت يمينًا أو يسارًا حسب موقعه. يعمل عبر WebRTC باستخدام PeerJS.
💤 الشخصية النائمة: إذا غيّرت التبويب أو فتحت يوتيوب، تنام شخصيتك عند الجميع (Page Visibility API). مؤشر «التركيز الجماعي» يعرض كم شخصًا مستيقظًا.
🌐 عربي وإنجليزي مع دعم RTL كامل.
📦 ملف واحد بلا بناء ولا تثبيت.
التشغيل محليًا
python3 -m http.server 8000
# افتح http://localhost:8000
المايكروفون يحتاج localhost أو HTTPS.

النشر على GitHub Pages
ارفع الملفين index.html وREADME.md إلى مستودع جديد.
من Settings ← Pages اختر الفرع main والمجلد / (root).
شارك الرابط مع رمز الغرفة، مثل: https://USER.github.io/REPO/#study-group
كيف يعمل
لا يوجد خادم خاص بنا. كل غرفة هي شبكة (Mesh) بين المتصفحات، وأول من يدخل يأخذ المعرّف pshall-<room>-0 والتالي -1 وهكذا.
يعتمد الاتصال الأولي على خادم PeerJS العام المجاني. للإنتاج استضف peerjs-server وأضف خادم TURN.
الحد الأقصى 12 شخصًا لكل غرفة لأن الشبكة Mesh.
خارطة الطريق
 دردشة نصية وإيموجي فوق الشخصيات
 تخصيص الشخصية وأزياء بيكسل
 مؤقت بومودورو مشترك
 غرف خاصة بكلمة مرور
 خريطة أكبر بغرف متعددة
English

A 2D pixel-art web space for studying and working with friends remotely. Walk in as an avatar, sit at a desk next to your friends, and hear them as if they were beside you.

Features
🎧 Spatial audio: voices get louder as you walk closer and fade as you move away, panned left or right by position. Built on WebRTC through PeerJS.
💤 Sleeping avatar: switch tabs or open YouTube and your avatar falls asleep for everyone (Page Visibility API). A "Group focus" meter shows how many people are awake.
🌐 Arabic and English with full RTL support.
📦 Single file, no build step.
Run locally
python3 -m http.server 8000
# open http://localhost:8000
The microphone needs localhost or HTTPS.

Deploy on GitHub Pages
Push index.html and README.md to a new repository.
Go to Settings → Pages, pick branch main and folder / (root).
Share the link plus a room code: https://USER.github.io/REPO/#study-group
How it works
There is no backend of our own. Each room is a browser-to-browser mesh. The first person claims the ID pshall-<room>-0, the next -1, and so on.
Signaling uses the free public PeerJS server. For production, self-host peerjs-server and add a TURN server.
Capped at 12 people per room because a mesh scales poorly.
Roadmap
 Text chat and emoji bubbles
 Avatar customization and pixel outfits
 Shared Pomodoro timer
 Password-protected rooms
 Larger multi-room map
License
MIT

v2 · Solo, daily trees & world ranking · الوضع الفردي والتصنيف العالمي
Solo / وحدي: open-ended time, tree grows with focused minutes. · الوقت مفتوح وتكبر الشجرة مع دقائق التركيز.
Daily tree / شجرة يومية: points and tree reset every UTC day, history kept locally. · تبدأ شجرة جديدة كل يوم.
PDF reader + pen: per-page highlights and an end-of-session book review. · قارئ PDF وقلم وتقييم في نهاية الجلسة.
World ranking / التصنيف العالمي: needs a free Firebase Realtime Database. Create one, set rules to {"rules":{"daily":{"$day":{"$uid":{".read":true,".write":true}}}}}, then paste its URL into const DB="" in index.html. Rules are open, so treat the ranking as casual.
Countries: edit EXC in index.html to change which countries are hidden from the picker.
v3 · Solo / Group split, pens, earthquakes · فردي وجماعي وأقلام وزلازل
Menu / القائمة: site name + profile (name, country, photo), then two separate modes: Solo (open time, daily tree, book + pen) and Group (voice, chat, quizzes, and everything below). · فردي وجماعي منفصلين.
Pens / الأقلام: pen, transparent highlighter, eraser, 10 preset colors + any color, 5 sizes. · قلم وشفاف وممحاة وألوان.
Group, second half / نصف الوقت الثاني: random earthquakes (red circles show where objects land, move away), bombs and swords (one use each; sword steals 5 points), and the 10-coin (+10) which always appears 15 s before the end and sometimes at random times. · زلازل وقنابل وسيوف وعملة 10.
Exit / الخروج: "End session" shows a timer, then final results and an exit-to-menu button. · إنهاء الجلسة بموقت ونتيجة نهائية.
Sprites (bomb, sword, coin) are embedded in index.html.
