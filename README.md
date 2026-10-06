# AHDownload

تطبيق أندرويد احترافي متقدم لتحميل الوسائط من منصات التواصل الاجتماعي.

## الميزات

- **مركز تحميل ذكي** بواجهة حديثة ومصقولة
- دعم **YouTube** الكامل عبر Player API
- كشف تلقائي للمنصات: YouTube · TikTok · Instagram · X · Facebook
- اختيار الجودات (4K / 1080p / 720p / صوت فقط)
- تحميل في الخلفية عبر WorkManager
- نظام تشخيص متقدم (Diagnostics)
- دعم Share Intent
- ثيم Dark / Light احترافي مع تدرجات

## التقنيات

| التقنية | الإصدار |
|---------|---------|
| Kotlin | 2.4.20 |
| Jetpack Compose + Material 3 | BOM 2026.09 |
| Android Gradle Plugin | 9.3.0 |
| Gradle | 9.5 |
| JVM | 17 |
| WorkManager | 2.12.0 |

## الهيكلة (Modular Clean Architecture)

```
AHDownload/
├── app/                  # Application shell + navigation
├── core/
│   ├── common/           # Shared primitives (AppResult, DiagnosticLog)
│   └── designsystem/     # Theme, Typography, reusable components
├── domain/               # Business logic
│   ├── analyzer/         # Link analysis & platform detection
│   ├── resolver/         # Media resolution (YouTube full support)
│   ├── download/         # Streaming download engine + queue
│   ├── validation/       # Candidate validation & media probe
│   └── url/              # URL normalization
└── feature/
    ├── welcome/          # Animated onboarding
    └── home/             # Smart download center (UI)
```

## البناء

```bash
./gradlew :app:assembleDebug
```

## الحالة الحالية

- الواجهة الرئيسية أعيد تصميمها بالكامل (Hero card، بطاقات جودات، حالات تحميل/خطأ/نجاح)
- YouTube Resolver يعمل
- باقي المنصات: كشف فقط (Resolvers قيد التطوير)
- تحميل خلفي + إشعارات جاهزة

## المخطط القادم

- `feature:downloads` — شاشة سجل التحميلات مع تقدم حي
- Resolvers لـ TikTok / Instagram / X
- `feature:history`
- دعم Playlist / Batch download
