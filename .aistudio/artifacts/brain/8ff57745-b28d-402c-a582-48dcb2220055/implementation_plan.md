# Interview & Career Coach Agent (Kariyer ve Mülakat Koçu)

Kullanıcının gireceği mülakattaki katılımcı unvanına (interviewer title) göre özel mülakat soruları ve STAR analizleri üreten, tamamlanan eğitim içeriklerini analiz ederek bir sonraki kariyer adımı için kişiselleştirilmiş eğitim ve gelişim yol haritası çıkaran profesyonel yapay zeka koçluk platformu.

> [!IMPORTANT] Kullanıcı Tercihleri ve Kararları (Aşama 1 Özeti)
> - **Mülakat Modülü Deneyimi**: Detaylı soru listesi, değerlendirme ölçütleri, örnek STAR yanıtları ve interaktif pratik/yanıt değerlendirme modu.
> - **Eğitim & Kariyer Modülü**: Kullanıcının tamamladığı eğitimlerin içeriklerini sentezleyerek derinlemesine beceri boşluğu analizi (skill gap analysis) ve adım adım kariyer/eğitim yol haritası.
> - **Dil Tercihi**: Modern Türkçe arayüz ve çift dil (Türkçe/İngilizce) içerik üretimi desteği.

---

### 1. Genel Bakış ve Temel Konsept (Overview & Core Concept)

- **Ne Yapar**:
  1. **Mülakat Simülatörü ve Soru Üretici**: Adayın gireceği mülakattaki katılımcının unvanına (örn. Engineering Manager, Senior HR Partner, Head of Product, Solution Architect, VP of Sales vb.), hedeflenen pozisyona ve kıdeme göre; o unvandaki kişinin soracağı spesifik soruları, arkasında yatan niyeti (interviewer's hidden agenda), kaçınılması gereken kırmızı bayrakları ve STAR metodolojisiyle kurgulanmış örnek yanıtları üretir. Kullanıcı aynı zamanda kendi cevabını yazıp anında yapay zeka geri bildirimi alabilir.
  2. **Eğitim Analizi ve Kariyer Yol Haritası (Next-Step Learning)**: Kullanıcının bugüne kadar aldığı eğitimleri, sertifikaları ve müfredat içeriklerini inceler; mevcut yetkinlik haritasını çıkarır, bir sonraki kıdem veya hedef rol için eksik kalan becerileri tespit eder ve somut bir sonraki eğitim müfredatı, sertifika önerileri ve pekiştirici proje fikirleri sunar.
- **Hedef Kitle**: Mülakatlara hazırlanan profesyoneller, kariyer değişikliği veya terfi hedefleyen uzmanlar ve sürekli gelişim yolunu planlayan mühendisler/yöneticiler.
- **Değer Önerisi**: Ezbere genel mülakat soruları yerine, karşıdaki unvanın bakış açısına (teknik lider vs İK vs C-level) göre özelleştirilmiş stratejik hazırlık ve tamamlanan eğitimlerin üzerine inşa edilmiş gerçekçi bir sonraki adım rehberliği.

---

### 2. Kullanıcı Deneyimi ve Görsel Tasarım (UX & Visual Design)

- **Kullanıcı Akışları**:
  - **Akış A (Mülakat Hazırlığı)**: Unvan girişi (otomatik önerilerle: HR Director, Tech Lead, Product Manager, vb.), hedef pozisyon ve şirket bağlamı seçimi -> "Soruları ve Stratejiyi Üret" -> Kategorize edilmiş sorular (Teknik/Yetkinlik, Davranışsal, Liderlik, Kültür Uyumu) -> Tıklanabilir soru kartları: Neden bu soru sorulur?, Beklenen yetkinlikler, STAR model yanıtı -> İnteraktif "Cevabımı Test Et" alanı ve yapay zeka geri bildirimi.
  - **Akış B (Eğitim & Kariyer Yol Haritası)**: Tamamlanan eğitimleri ekleme (Başlık, Konu Başlıkları/Müfredat, Kazanılan Beceriler; hazır örnek şablonlarla hızlı test) -> Mevcut pozisyon ve hedef pozisyon seçimi -> "Eğitimleri ve Kariyer Adımını Analiz Et" -> 3 boyutlu analiz: 1) Kazanılmış Yetkinlik Özeti, 2) Beceri Boşluğu (Gap Analysis), 3) "Bir Sonraki Eğitim" Müfredat Taslağı, Sertifikasyonlar ve Pratik Proje Önerisi.
  - **Akış C (Kariyer Dosyası / Kayıtlar)**: Oluşturulan soru setlerini ve kariyer planlarını tek tıkla dışa aktarma (PDF/Markdown) ve geçmişi yerel olarak saklama.

- **Görsel Kimlik & Tema (Visual Theme)**:
  - *Stil Yönü*: Güven veren, modern kurumsal ve yönetici seviyesinde estetik (Executive Intelligence Workbench).
  - *Renk Paleti (60-30-10 Disiplini)*:
    - `%60 Nötr Zemin`: Temiz beyaz ve sofistike açık arduvaz (`bg-slate-50`, `bg-white`).
    - `%30 Yapısal Yüzeyler`: Yumuşak sınır çizgileri (`border-slate-200/80`), derin lacivert/slate metin hiyerarşisi (`text-slate-900`, `text-slate-600`).
    - `%10 Vurgu`: Prestijli kobalt mavisi (`bg-indigo-600` / `hover:bg-indigo-700`) ve zümrüt yeşili başarı göstergeleri.
  - *Tipografi*: Başlıklarda ve marka alanında modern `Plus Jakarta Sans`, veri ve metriklerde `tabular-nums` / `font-mono`.
  - *Tasarım Kuralları*: Asla gereksiz dekoratif hap rozetler veya rastgele nabız atan noktalar kullanılmayacak. Tüm etiketler yalın metin ve temiz tipografik ayrıştırıcılarla (`·`, `/`) sunulacak.

---

### 3. Temel Ürün Kararları & Tercihler (Product Decisions & Trade-Offs)

1. **Yapay Zeka Modeli (`gemini-3.8-flash`)**:
   - *Seçim*: Google GenAI SDK ile `gemini-3.8-flash` modeli sunucu tarafında (`server-side proxy`) JSON şemaları ve zengin metin üretimiyle kullanılacak.
   - *Gerekçe*: Hızlı yanıt süresi, yüksek muhakeme yeteneği ve yapılandırılmış JSON çıktı güvenilirliği.
2. **Hazır Örnekler & Şablonlar (Instant Demo Profiles)**:
   - *Seçim*: Kullanıcının hemen deneyebilmesi için popüler interviewer unvanları (örn. "Engineering Manager", "Head of People & Culture", "Staff Software Architect", "Product Director") ve gerçekçi tamamlanmış eğitim paketleri (örn. "Full-Stack Web Bootcamp + AWS Cloud Practitioner", "Veri Analitiği & SQL + Power BI") hazır tek tıkla doldurma butonlarıyla sunulacak.
3. **İnteraktif STAR Cevap Koçu**:
   - *Seçim*: Kullanıcı seçtiği bir soruya kendi yanıtını girdiğinde, koç cevabı S-Durum, T-Görev, A-Eylem, R-Sonuç kriterlerine göre puanlar ve düzeltilmiş profesyonel bir versiyon önerir.
4. **Veri Saklama**:
   - *Seçim*: Tarayıcı oturumunda `localStorage` ile güvenli ve anında kalıcı geçmiş saklama; sunucu tarafında API anahtarı güvenliğini koruyan Node/Express proxy mimarisi.

---

### 4. Teknik Mimari ve Veri Stratejisi (Technical Architecture & Data Strategy)

```
┌────────────────────────────────────────────────────────────────────────┐
│                        Tarayıcı (Client React UI)                      │
│                                                                        │
│  ┌───────────────────────┐  ┌────────────────────────────────────────┐ │
│  │   Üst Çubuk / Sekmeler│  │  Aktif Modül Görünümü                  │ │
│  │   · Mülakat Koçu      │  │  - Interviewer Form & Rol Seçimi        │ │
│  │   · Eğitim & Yol Haritası│- Soru Kartları (STAR & Red Flags)       │ │
│  │   · Cevap Pratiği     │  │  - Tamamlanan Eğitimler & Müfredat Girişi│ │
│  │   · Kayıtlı Oturumlar │  │  - Beceri Boşluğu & Sonraki Eğitim Planı│ │
│  └───────────────────────┘  └────────────────────────────────────────┘ │
└────────────────────────────────────┬───────────────────────────────────┘
                                     │ JSON HTTP POST (/api/*)
                                     ▼
┌────────────────────────────────────────────────────────────────────────┐
│                 Full-Stack Node.js / Express Server API                │
│                                                                        │
│   POST /api/interview/generate-questions                               │
│        └──> Gemini 3.8 Flash (Interviewer Title & Context Prompting)   │
│   POST /api/interview/evaluate-answer                                  │
│        └──> Gemini 3.8 Flash (STAR Methodology Assessment)             │
│   POST /api/career/analyze-roadmap                                     │
│        └──> Gemini 3.8 Flash (Curriculum Gap Analysis & Next Courses)  │
│                                                                        │
│   Environment: process.env.GEMINI_API_KEY (Server-Side Only)           │
└────────────────────────────────────────────────────────────────────────┘
```

- **Veri Modelleri**:
  - `InterviewQuestion`: id, question, questionType (behavioral, technical, situational, culture), whyInterviewerAsks, lookFors, redFlags, starSampleAnswer.
  - `AnswerEvaluation`: scoreBreakdown (situation, task, action, result), overallFeedback, strengths, areasToImprove, refinedAnswer.
  - `CareerRoadmap`: acquiredSkillsSummary, missingSkills, nextRecommendedCourse (title, comprehensiveSyllabus, keyMilestones, durationEst), recommendedCertifications, portfolioProjectIdea.
