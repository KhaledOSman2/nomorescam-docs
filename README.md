# No More Scam - معاً ضد الاحتيال 🛡️

<div align="center">

منصة إلكترونية شاملة لمشاركة تجارب الاحتيال والإبلاغ عن المحتالين لحماية المجتمع من تكرار حالات الغش والاحتيال.

**Full-Stack Web Application | React + TypeScript + Node.js + MongoDB**

</div>

---

## 📋 جدول المحتويات

- [نظرة عامة](#-نظرة-عامة)
- [البنية المعمارية](#-البنية-المعمارية)
- [التقنيات المستخدمة](#-التقنيات-المستخدمة)
- [بنية المشروع](#-بنية-المشروع)
- [المميزات الرئيسية](#-المميزات-الرئيسية)
- [التثبيت والإعداد](#-التثبيت-والإعداد)
- [الأمان والحماية](#-الأمان-والحماية)

---

## 🎯 نظرة عامة

**No More Scam** هي منصة مجتمعية متكاملة تتكون من:

- **Frontend Application**: تطبيق ويب حديث مبني بـ React و TypeScript
- **Backend API**: خادم RESTful API مبني بـ Node.js و Express
- **Database Layer**: قاعدة بيانات MongoDB مع Redis للتخزين المؤقت
- **Cloud Services**: Cloudinary لإدارة الصور

### الهدف من المشروع
- توثيق حالات الاحتيال وبناء قاعدة بيانات مركزية
- حماية المستخدمين من التعرض للاحتيال المتكرر
- توفير نظام مراجعة دقيق للحد من البلاغات الكاذبة
- دعم كامل للغة العربية مع واجهة RTL احترافية

## 🏗️ البنية المعمارية

المشروع يتبع معمارية **Client-Server Architecture** مع فصل كامل بين Frontend و Backend:

```
┌─────────────────────────────────────────────────────────────┐
│                      FRONTEND (React)                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │   Pages      │  │  Components  │  │   Services   │     │
│  │  (Routing)   │  │   (UI/UX)    │  │  (API Calls) │     │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘     │
│         │                  │                  │             │
│         └──────────────────┴──────────────────┘             │
│                           │                                 │
│                    Axios (HTTP Client)                      │
└───────────────────────────┼─────────────────────────────────┘
                            │
                     REST API (JSON)                          
                            │
┌───────────────────────────┼─────────────────────────────────┐
│                    BACKEND (Node.js)                        │
│                           │                                 │
│  ┌──────────────┬─────────┴────────┬──────────────┐        │
│  │   Routes     │   Controllers    │  Middleware  │        │
│  │  (Endpoints) │    (Business)    │  (Security)  │        │
│  └──────┬───────┴────────┬─────────┴──────┬───────┘        │
│         │                │                 │                │
│  ┌──────┴───────┬────────┴────────┬────────┴───────┐       │
│  │   Models     │    Services     │   Validators   │       │
│  │  (Mongoose)  │  (Logic Layer)  │     (Joi)      │       │
│  └──────┬───────┴─────────────────┴────────────────┘       │
└─────────┼──────────────────────────────────────────────────┘
          │
    ┌─────┴──────┬──────────────┬──────────────┐
    │  MongoDB   │  Cloudinary  │    Redis     │
    │ (Database) │   (Images)   │   (Cache)    │
    └────────────┴──────────────┴──────────────┘
```

### تدفق البيانات (Data Flow)

1. **User Interaction**: المستخدم يتفاعل مع واجهة React
2. **State Management**: Zustand يدير الحالة العامة للتطبيق
3. **API Calls**: Axios يرسل طلبات HTTP إلى Backend
4. **Authentication**: JWT tokens للمصادقة والترخيص
5. **Routing**: Express يوجه الطلبات إلى Controllers المناسبة
6. **Validation**: Joi يتحقق من صحة البيانات
7. **Business Logic**: Controllers تنفذ المنطق التجاري
8. **Data Access**: Mongoose يتفاعل مع MongoDB
9. **Response**: البيانات ترجع بصيغة JSON إلى Frontend

---

## 🛠️ التقنيات المستخدمة

### Frontend Stack

#### Core Technologies

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **React** | 18.2.0 | مكتبة بناء واجهة المستخدم - توفر Component-based architecture و Virtual DOM لأداء عالي |
| **TypeScript** | 5.2.2 | لغة برمجة مكتوبة - تضيف Type Safety وتقلل الأخطاء في وقت التطوير |
| **Vite** | 5.1.4 | أداة بناء سريعة - Hot Module Replacement فوري و Build سريع جداً |

#### UI & Styling

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **TailwindCSS** | 3.4.1 | إطار عمل CSS Utility-First - تصميم سريع ومرن مع دعم RTL للعربية |
| **Lucide React** | 0.344.0 | مكتبة أيقونات - أيقونات SVG خفيفة وقابلة للتخصيص |
| **Cairo Font** | - | خط عربي احترافي - قراءة واضحة ومريحة للعين |

#### Routing & Navigation

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **React Router** | 6.22.0 | إدارة التوجيه - Client-side routing مع Protected Routes |

#### State Management

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Zustand** | 4.5.0 | إدارة الحالة العامة - بديل خفيف لـ Redux، API بسيط وسهل الاستخدام |

#### Forms & Validation

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **React Hook Form** | 7.50.1 | إدارة النماذج - أداء عالي مع Re-renders قليلة |
| **Zod** | 3.22.4 | التحقق من البيانات - Type-safe validation schemas |
| **@hookform/resolvers** | 3.3.4 | دمج Zod مع React Hook Form |

#### HTTP Client

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Axios** | 1.6.7 | مكتبة HTTP - Interceptors للمصادقة، معالجة أخطاء متقدمة |

#### Utilities

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **date-fns** | 3.3.1 | معالجة التواريخ - مكتبة خفيفة مع دعم i18n |
| **clsx** | 2.1.0 | دمج CSS classes بشكل شرطي |
| **tailwind-merge** | 2.2.1 | دمج Tailwind classes بدون تعارضات |

#### Analytics

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Vercel Analytics** | 1.5.0 | تحليلات الأداء والاستخدام |

---

### Backend Stack

#### Core Technologies

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Node.js** | 18+ | بيئة تشغيل JavaScript - أداء عالي و Non-blocking I/O |
| **Express** | 4.18.2 | إطار عمل الخادم - مرن وسهل الاستخدام مع Middleware قوي |
| **TypeScript** | 5.3.3 | لغة برمجة مكتوبة - Type Safety في Backend أيضاً |

#### Database

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **MongoDB** | 8.0.3 | قاعدة بيانات NoSQL - مرونة في Schema، أداء عالي للقراءة |
| **Mongoose** | 8.0.3 | ODM لـ MongoDB - Schema validation، Middleware، Population |
| **Redis** | 4.6.11 | قاعدة بيانات In-Memory - Caching للبيانات المتكررة، Session storage |

#### Authentication & Security

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **jsonwebtoken** | 9.0.2 | JWT tokens - Stateless authentication |
| **bcryptjs** | 2.4.3 | تشفير كلمات المرور - Hashing آمن مع Salt |
| **Helmet** | 7.1.0 | حماية HTTP headers - منع ثغرات XSS، Clickjacking، إلخ |
| **express-rate-limit** | 7.1.5 | Rate limiting - حماية من DDoS و Brute force |
| **express-mongo-sanitize** | 2.2.0 | منع NoSQL injection |
| **sanitize-html** | 2.11.0 | تنظيف HTML من XSS |
| **validator** | 13.11.0 | التحقق من البيانات (emails، URLs، إلخ) |

#### File Upload & Storage

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Multer** | 1.4.5 | رفع الملفات - Middleware لمعالجة multipart/form-data |
| **Cloudinary** | 1.41.0 | تخزين الصور - CDN سريع، معالجة صور تلقائية، تحسين الأداء |
| **file-type** | 16.5.4 | التحقق من نوع الملف - كشف MIME type الحقيقي |

#### Validation

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Joi** | 17.11.0 | التحقق من البيانات - Schema validation قوي ومرن |

#### Logging & Monitoring

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Winston** | 3.11.0 | نظام السجلات - Logging متعدد المستويات مع Transports مختلفة |
| **Morgan** | 1.10.0 | HTTP request logger - تسجيل جميع الطلبات |

#### Email

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **Nodemailer** | 6.9.7 | إرسال البريد الإلكتروني - دعم SMTP، تأكيد الحساب، إعادة تعيين كلمة المرور |

#### Utilities

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **dotenv** | 16.3.1 | إدارة متغيرات البيئة |
| **cors** | 2.8.5 | Cross-Origin Resource Sharing |
| **compression** | 1.7.4 | ضغط HTTP responses - تقليل حجم البيانات المنقولة |
| **express-async-handler** | 1.2.0 | معالجة Async errors تلقائياً |
| **date-fns** | 2.30.0 | معالجة التواريخ |
| **uuid** | 9.0.1 | توليد معرفات فريدة |

#### Development Tools

| التقنية | الإصدار | الاستخدام والسبب |
|---------|---------|------------------|
| **ts-node-dev** | 2.0.0 | تشغيل TypeScript مع Hot reload |
| **ESLint** | 8.56.0 | Linting للكود - الحفاظ على جودة الكود |
| **Jest** | 29.7.0 | Testing framework |
| **ts-jest** | 29.1.1 | Jest مع TypeScript |

---

## 📁 بنية المشروع

### Frontend: React + TypeScript
- **Components**: مكونات UI قابلة لإعادة الاستخدام (Layout, Forms, UI Elements)
- **Pages**: صفحات التطبيق (Home, Reports, Search, Dashboard)
- **Services**: طبقة API للتواصل مع Backend
- **Store**: إدارة الحالة باستخدام Zustand
- **Utils**: دوال مساعدة وثوابت

### Backend: Node.js + Express
- **Models**: نماذج Mongoose (User, Report, Scammer)
- **Controllers**: معالجات الطلبات والمنطق التجاري
- **Routes**: تعريف Endpoints
- **Middleware**: المصادقة، التحقق، الأمان
- **Services**: خدمات الأعمال (Email, Upload, Matching)
- **Validators**: مخططات التحقق باستخدام Joi

---

## ✨ المميزات الرئيسية

### للمستخدمين
- 📝 إنشاء بلاغات مفصلة مع صور
- 🔍 بحث متقدم عن المحتالين
- 📊 لوحة تحكم شخصية
- ⚙️ إدارة الحساب والإعدادات

### للمسؤولين
- 📈 لوحة تحكم شاملة مع إحصائيات
- ✅ مراجعة وقبول/رفض البلاغات
- 👤 إدارة المحتالين والمستخدمين
- 📄 تقارير مفصلة

---

## 🔒 الأمان والحماية

- **JWT Authentication**: مصادقة آمنة
- **bcrypt**: تشفير كلمات المرور
- **Helmet.js**: حماية HTTP headers
- **Rate Limiting**: حماية من DDoS
- **Input Validation**: Joi + Zod
- **XSS Prevention**: تنظيف HTML
- **NoSQL Injection Prevention**: تنظيف المدخلات
- **CORS**: إدارة محكمة للطلبات

---

## 🚀 التثبيت والإعداد

### 1. Frontend Setup
```bash
npm install
# إنشاء ملف .env
echo "VITE_API_URL=http://localhost:5000" > .env
npm run dev
```

### 2. Backend Setup
```bash
cd backend
npm install
# إعداد ملف .env (انظر backend/.env.example)
npm run dev
```

### متطلبات البيئة
- Node.js 18+
- MongoDB 6.0+
- Redis 7.0+ (اختياري)
- Cloudinary Account

---

## 📚 الوثائق الإضافية

للمزيد من التفاصيل، راجع:
- `backend/README.md` - وثائق Backend API
- `backend/src/routes/` - تفاصيل Endpoints
- `src/services/` - تفاصيل Frontend Services

---

## 📄 الترخيص

MIT License - مشروع مفتوح المصدر

---

## 🤝 المساهمة

نرحب بالمساهمات! يرجى فتح Issue أو Pull Request.

---

**Built with ❤️ for the Arabic community**
