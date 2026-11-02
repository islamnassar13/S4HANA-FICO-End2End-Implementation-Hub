# 🏆 الدليل الاحترافي الشامل: أهم 100 سؤال وجواب في مقابلات SAP FICO
## *The 100 Important SAP FICO Interview Questions & Answers — With Expert Evaluation & S/4HANA Enhancements*

> [!IMPORTANT]
> **دليل التمييز البصري في هذا المستند (Visual Legend):**
> تم تصميم هذا الدليل ليفصل بوضوح تام بين **النص الأصلي الوارد في الملف المرفق** وبين **التقييم الفني والإضافات التحسينية المضافة من طرفنا**:
> - 📄 **[النص الأصلي من الملف — Original PDF Text]:** معروض داخل اقتباس مخصص بنفس نص السؤال والإجابة الأصلية باللغة الإنجليزية دون تغيير في المعنى (مع تنقية أخطاء المسح الضوئي OCR فقط).
> - 🎯 **[تقييم الإجابة — Answer Evaluation Badge]:** تقييم رقمي وبصري (`🟢 ممتازة` | `🟡 جيدة وتحتاج لتفصيل/تحديث` | `🔴 غير دقيقة وتحتاج لتصحيح`).
> - ✨ **[التحسين والإضافة المهنية — Added Expert Enhancement]:** معروض داخل صندوق ملاحظات مستقل يتضمن الأكواد التقنية (`T-Codes`)، الجداول، التصحيحات المفاهيمية، وتحديثات **SAP S/4HANA**.

## 📊 لوحة الملخص التنفيذي لتقييم إجابات الملف الأصلي (Executive Evaluation Summary)

| الفئة التقييمية (Evaluation Category) | الرمز البصري | عدد الإجابات | النسبة المئوية | أبرز الملاحظات الفنية (Key Technical Findings) |
| :--- | :---: | :---: | :---: | :--- |
| **إجابات ممتازة ودقيقة (4.0 - 5.0 / 5)** | 🟢 | **76 سؤالاً** | **76%** | تعريفات سليمة ومباشرة، ولكنها تفتقر غالباً لذكر أكواد المعاملات (`T-Codes`) التي يُسأل عنها في المقابلات العملية. |
| **إجابات متوسطة تحتاج لتفصيل أو تحديث (3.0 - 3.5 / 5)** | 🟡 | **21 سؤالاً** | **21%** | إجابات مختصرة جداً أو مبنية على إصدار `SAP ECC` القديم وتحتاج إلى تحديث جوهري لتواكب `SAP S/4HANA` ومعيار `IFRS 16`. |
| **إجابات غير دقيقة تحتاج لتصحيح مفاهيمي (< 3.0 / 5)** | 🔴 | **3 أسئلة** | **3%** | تشمل الأسئلة **#27** (العملات الموازية)، **#30** (دليل الحسابات والمبادئ المحاسبية)، مع خلط جزئي في **#4** و **#54**. |

> [!WARNING]
> **أهم 6 ملاحظات وتصحيحات جوهرية يجب الانتباه لها قبل أي مقابلة عمل (Critical Interview Alerts):**
> 1. **السؤال #30 (Chart of Accounts):** يذكر الملف الأصلي أن كل مبدأ محاسبي (Accounting Principle) يتطلب إنشاء دليل حسابات جديد، وهذا **غير دقيق في SAP**؛ حيث يمكن استخدام نفس دليل الحسابات التشغيلي مع الدفاتر المتوازية (**Parallel Ledgers**).
> 2. **السؤال #27 (Parallel Currency):** يذكر الملف أنها تُستخدم لإجراء المعاملات الأجنبية، بينما الأدق أن المعاملات الأجنبية تتم بعملة المستند (`Document Currency`)، أما **Parallel Currency** فتُستخدم للتقييم المتوازي والتجميع المالي للمجموعة (Group Consolidation).
> 3. **السؤال #77 (Secondary Cost Elements):** يذكر الملف أنها لا يمكن أن تُعرّف كحسابات أستاذ عام (G/L Accounts)؛ وهذا كان صحيحاً في `SAP ECC` فقط، أما في **`SAP S/4HANA`** فقد تم دمجها وأصبحت تُنشأ كحسابات أستاذ عام في `FS00`.
> 4. **السؤال #24 (Company Code Currencies):** الحد الأقصى في `ECC` هو 3 عملات، بينما في **`S/4HANA`** وصل إلى **10 عملات** لكل Ledger في جدول `ACDOCA`.
> 5. **السؤال #54 (Bank Key):** يضع الملف الأصلي عبارة `(account number)` بجانب Bank Key؛ والصحيح أن **Bank Key** هو كود تعريف فرع البنك، بينما رقم الحساب البنكي يُعرّف داخل **House Bank Account ID**.
> 6. **السؤال #67 (Real Internal Order):** يحصر الملف الأصلي استخدامها في المعاملات المرتبطة بالأصول، بينما هي أداة عامة لتتبع التسويق، الصيانة، الفعاليات، والأصول تحت الإنشاء.

## 🛠️ جدول مرجعي سريع لأهم أكواد SAP FICO المضافة في التحسينات (Quick T-Code Cheat Sheet)

| المجال (Area) | أكواد التهيئة (Configuration T-Codes) | أكواد المستخدم النهائي (End-User / Master Data T-Codes) |
| :--- | :--- | :--- |
| **الهيكل التنظيمي (Org Structure)** | `OX02` (Company Code), `OKKP` (Controlling Area), `KEA0` (Operating Concern), `OX03` (Business Area), `OB45` (Credit Control) | `EC01` (Copy Company Code), `SCC4` (Client Maintenance) |
| **الأستاذ العام والإعدادات (FI-GL)** | `OB13` (COA), `OBD4` (Account Group), `OB29` (Fiscal Year), `OBBO`/`OB52` (Posting Periods), `OBC4` (Field Status), `OBA7` (Doc Type), `OBA4` (Tolerance), `OB58` (FSV) | `FS00` (G/L Master), `FBD1`/`F.14` (Recurring), `FBS1`/`F.81` (Accrual), `F.01` (Financial Statements), `FAGLGVTR` (GL Carryforward) |
| **الموردون والعملاء والبنوك (AP/AR/BL)** | `OBD3` (Vendor Grp), `OBD2` (Customer Grp), `OBB8` (Payment Terms), `FBKP` (Special GL), `FBZP` (APP Config), `FBMP` (Dunning), `FBCJC0` (Cash Journal Config) | `BP` (Business Partner), `F110` (Auto Payment), `F-53` (Manual Payment), `F150` (Dunning Run), `FBCJ` (Cash Journal), `FI01`/`FI12` (Banks), `F.07` (AR/AP Carryforward) |
| **الأصول الثابتة (FI-AA)** | `EC08` (Chart of Dep.), `OAOB` (Assign COD), `OAOA` (Asset Class), `AO90` (Account Det.), `AFAMA` (Depreciation Key) | `AS01` (Asset Master), `AFAB` (Depreciation Run), `AJAB`/`FAA_CMP` (Year-End Closing) |
| **المحاسبة الإدارية والربحية (CO-OM / CO-PA)** | `OKEON` (Standard Hierarchy), `KEA5` (Characteristics), `KEA6` (Value Fields) | `KS01` (Cost Center), `KE51` (Profit Center), `KO01`/`KO88` (Internal Order & Settlement), `KL01`/`KP26` (Activity Type & Planning), `KK01` (SKF) |
| **تكاليف المنتجات والتصنيع (CO-PC / PP)** | `OKKN` (Costing Variant), `OKTZ` (Cost Component Structure), `OBYC` (MM-FI Auto Posting) | `CS01` (BOM), `CA01` (Routing), `CK11N` (Single Cost Estimate), `CK24` (Mark/Release), `CK40N` (Costing Run), `KKS2` (Variances), `CKMLCP` (Actual Costing/ML) |

## 🏛️ القسم الأول: أساسيات SAP FICO والهيكل التنظيمي (Organizational Structure)
*يركز هذا القسم على المفاهيم التأسيسية لموديولي المحاسبة المالية (FI) والرقابة الإدارية (CO)، والوحدات التنظيمية (Client, Company Code, Controlling Area, Operating Concern, Business Area, Segment).*

### 🔹 #1. What is SAP FICO?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #1:** What is SAP FICO?
> **Answer:** SAP FICO is an acronym that stands for “Financial Accounting” and “Controlling.” SAP FI and SAP CO are important fundamental modules in SAP that work together to help business organizations maintain and create financial statements for better decision-making and reporting.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — إجابة تأسيسية جيدة ولكنها عامة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الإجابة صحيحة كمفهوم عام، لكن في مقابلات العمل يفضل توضيح الفرق الجوهري: **SAP FI** يركز على التقارير المالية الخارجية الإلزامية (External Reporting مثل الميزانية العمومية وقائمة الدخل وفق معايير IFRS/GAAP)، بينما **SAP CO** يركز على التقارير الإدارية الداخلية وتحليل التكاليف والربحية (Internal Management Reporting). في **SAP S/4HANA**، تم دمجهما في جدول واحد موحد هو **ACDOCA (Universal Journal)**.

### 🔹 #2. What are the Sub-Modules of SAP FI?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #2:** What are the Sub-Modules of SAP FI?
> **Answer:** the important sub-modules of SAP FI are as follows:
> - General Ledger Accounting
> - Accounts Payable
> - Accounts Receivable
> - Bank Accounting
> - Asset Accounting

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة ومباشرة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يمكن تعزيز الإجابة بذكر الاختصارات الرسمية وبعض الموديولات الفرعية الإضافية لمستوى Senior: **FI-GL** (الأستاذ العام)، **FI-AP** (الموردين)، **FI-AR** (العملاء)، **FI-BL** (البنوك)، **FI-AA** (الأصول الثابتة)، بالإضافة إلى **FI-TV** (إدارة السفر) و **FI-SL** (الأستاذ الخاص - Special Purpose Ledger).

### 🔹 #3. What Other Modules are Connected with ‘FICO’?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #3:** What Other Modules are Connected with ‘FICO’?
> **Answer:** The other modules which are connected with FICO are as follows:
> - Material Management (MM)
> - Production Planning (PP)
> - Sales and Distribution (SD)
> - Logistic Execution (LE)
> - Human Resource (HR)

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — صحيحة ولكن تنقصها نقاط الربط التقنية (Integration Points)`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الممتحن غالباً يسأل بعد هذا السؤال: *كيف يتم الربط؟* لذا يفضل إضافة الأكواد: الربط مع **MM** يتم عبر `OBYC` (توجيه الحسابات التلقائي لحركات المخزون والفواتير)، والربط مع **SD** يتم عبر `VKOA` (تحديد حسابات الإيرادات والخصومات)، والربط مع **PP** عبر تكاليف أوامر الإنتاج، والربط مع **HR/HCM** عبر ترحيل الرواتب (`PCP0`).

### 🔹 #4. What are the Organizational Elements in SAP FI?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #4:** What are the Organizational Elements in SAP FI?
> **Answer:** The organizational elements in SAP FI are as follows:
> - Company Code
> - Business Area
> - Chart of Accounts
> - Functional Area

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — تحتاج إلى دقة في التصنيف`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **تنبيه تقني:** الـ **Chart of Accounts** والـ **Functional Area** يُصنفان تقنياً كـ Master Data / Configuration Objects وليسوا وحدات تنظيمية (Organizational Units) بحتة في الهيكل التنظيمي. الوحدات التنظيمية الأساسية في FI هي: **Client**، **Company** (Group)، **Company Code**، **Business Area**، **Segment**، **Credit Control Area**، و **Financial Management Area**.

### 🔹 #5. What is a Client?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #5:** What is a Client?
> **Answer:** The SAP Client is the highest hierarchical organizational unit in an SAP system, containing master records and tables.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُفضل إضافة أن الـ **Client** يُعرّف برمز مكون من 3 خانات (مثل 100، 200)، وأن البيانات على مستوى الـ Client (Client-dependent data) تكون مشتركة بين جميع الشركات (Company Codes) الموجودة تحته، مثل البيانات العامة للعملاء والموردين ودليل الحسابات.

### 🔹 #6. What is Company Code?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #6:** What is Company Code?
> **Answer:** The company code is the smallest external accounting organizational unit for which a completely self-contained set of accounts can be created. This is a legal entity in its own right.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة نموذجية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة ممتازة ومطابقة لتعريف SAP الرسمي. يمكن فقط ذكر كود الإنشاء السريع للمقابلات: **T-Code: `OX02`** (أو النسخ عبر `EC01`) ورمزها المكون من 4 خانات Alpha-numeric.

### 🔹 #7. What is Controlling Area?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #7:** What is Controlling Area?
> **Answer:** The controlling area is the central organizational unit of the Controlling (CO) component, which is responsible for cost accounting. One or more company codes can be assigned to a single controlling area.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** لجعل الإجابة كاملة، اذكر شروط ربط أكثر من Company Code بنفس الـ Controlling Area (Cross-Company Code Cost Accounting): يجب أن يشتركوا جميعاً في نفس دليل الحسابات التشغيلي (**Operating Chart of Accounts**) ونفس متغير السنة المالية (**Fiscal Year Variant**). (**T-Code: `OKKP`**).

### 🔹 #8. What is Operating Concern?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #8:** What is Operating Concern?
> **Answer:** The Operating Concern is the organizational unit in which SAP Profitability Analysis is performed. Profitability analysis is used to generate granular profitability reports based on multiple dimensions such as customer, material, and so on.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يمكن إضافة أن الـ **Operating Concern** هي أعلى وحدة تنظيمية في موديول الرقابة (CO) وتحديداً في **CO-PA**، ويمكن ربط أكثر من Controlling Area بـ Operating Concern واحدة (**T-Code: `KEA0`**).

### 🔹 #9. What is Business Area?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #9:** What is Business Area?
> **Answer:** In SAP, a business area is an organizational unit within accounting that can be classified geographically or by-product based on the needs of the corporation. You prepare financial statements comprising balance sheet and profit & loss account for internal reporting under the business area.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — جيدة ولكن ينقصها سياق S/4HANA الحديث`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الإجابة صحيحة تاريخياً في SAP ECC (وتُعرّف عبر **`OX03`** وتكون غير مرتبطة بـ Company Code محددة)، ولكن في **SAP New GL** و **S/4HANA**، أصبح استخدام **Segment** و **Profit Center** مع خاصية Document Splitting هو الممارسة القياسية الموصى بها بدلاً من Business Area.

### 🔹 #10. What is Credit Control Area?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #10:** What is Credit Control Area?
> **Answer:** A credit controlling Area is an organizational unit or area of responsibility established to manage customer credit limits. Only one credit control area can be assigned to a single company code in SAP. Many company codes, however, can be assigned to the same credit control area. Aside from that, the credit-control area can be derived from the sales area.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — صحيحة في ECC ولكن تغيرت في S/4HANA`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الإجابة تشرح Credit Control Area الكلاسيكية (`OB45` / `FD32`). في **SAP S/4HANA**، تم استبدال FI-AR Credit Management التقليدي بـ **SAP Credit Management (FIN-FSCM-CR)** حيث يتم إدارة الائتمان عبر **Credit Segments** داخل بيانات شريك الأعمال (**Business Partner - BP**).

### 🔹 #11. What is Financial Management Area in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #11:** What is Financial Management Area in SAP?
> **Answer:** In SAP, a financial management area is an organizational unit that organizes the business in terms of cash management and funds management.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة ومختصرة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرّف بـ 4 خانات عبر **`OF01`** وترتبط بموديولات **Treasury / Cash Management** و **Funds Management (FM - الموازنات)**. يمكن ربط أكثر من Company Code بـ FM Area واحدة.

### 🔹 #12. What is the Default Exchange Rate Type used in all SAP Transactions?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #12:** What is the Default Exchange Rate Type used in all SAP Transactions?
> **Answer:** The default exchange rate for all SAP transactions is M (Average Rate).

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة دقيقة ومباشرة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة صحيحة تماماً. للتوسع في المقابلة: هناك أيضاً الأنواع القياسية الأخرى مثل **G** (سعر الشراء للبنك - Bank Buying Rate) و **B** (سعر البيع للبنك - Bank Selling Rate)، ويتم تعريف أسعار الصرف في جدول `TCURR` عبر **`OB08`**.

### 🔹 #13. What is Segment?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #13:** What is Segment?
> **Answer:** In accounting, a segment is an organizational unit that can be used for both internal and external reporting. At the segment level, both profit and loss and balance sheet reporting will be available.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُفضل توضيح أن الـ **Segment** يُشتق تلقائياً من الـ **Profit Center** (يتم تعيينه داخل شاشة بيانات مركز الربحية `KE51`)، ويُستخدم لتلبية متطلبات التقارير القطاعية (Segment Reporting) وفق معيار **IFRS 8** و **US GAAP (ASC 280)** بالاعتماد على **Document Splitting**.

## 📘 القسم الثاني: الأستاذ العام، الإعدادات العامة، والعملات (General Ledger & Global Settings)
*يغطي هذا القسم إعدادات الأستاذ العام (FI-GL)، مجموعات الحسابات، متغيرات السنة المالية وفترات الترحيل، العملات الموازية، الدفاتر المتوازية (Parallel Ledgers)، قيود الاستحقاق، وأنشطة إقفال نهاية العام.*

### 🔹 #14. What is an Account Group?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #14:** What is an Account Group?
> **Answer:** An account group is a method of separating or grouping similar accounts into a single group. In SAP, each account group is associated with a chart of accounts, thus you can only utilize account group if the controlling areas have the same chart of accounts.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — تنقصها أهم وظيفتين تقنيتين للـ Account Group`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في المقابلات، أهم نقطتين يجب ذكرهما عن **G/L Account Group (`OBD4`)** هما:
> 1. تحديد **نطاق أرقام الحسابات (Number Range)** للحسابات المنشأة ضمن المجموعة.
> 2. التحكم في **حالة الحقول (Field Status)** لشاشة البيانات الرئيسية للحساب على مستوى الشركة (Company Code Segment في `FS00`).

### 🔹 #15. What are Tolerance Groups for Employees?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #15:** What are Tolerance Groups for Employees?
> **Answer:** Employee tolerance groups in SAP establish the maximum limits for postings based on Amount per document, Amount per open item account, Cash discount, and Payment discrepancies.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة وافية وممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة دقيقة جداً وتغطي الأربعة محددات الرئيسية. أضف فقط الكود التقني: يتم تعريفها عبر **`OBA4`** وتعيين المستخدمين لها عبر **`OB57`**، وفي حال عدم تعيين مجموعة لموظف، يطبق النظام المجموعة الفارغة (Blank Tolerance Group) كافتراضية.

### 🔹 #16. What is a Risk Category?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #16:** What is a Risk Category?
> **Answer:** You can categorize customers using risk categories, such as low-risk customers, medium-risk customers, high-risk customers, and so on.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — عامة جداً وتحتاج ربط بإدارة الائتمان`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** اذكر أن **Risk Category** تُعرّف في **`OB01`** وتُربط بـ Credit Control Area (أو Credit Profile في S/4HANA FSCM)، وتتحكم مباشرة في كيفية تفاعل النظام تلقائياً مع طلبات البيع (Sales Orders) عند تجاوز حد الائتمان (تحذير، أو حظر تسليم، أو حظر أمر البيع).

### 🔹 #17. What is a Functional Area?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #17:** What is a Functional Area?
> **Answer:** A functional area is used to categorize operating expenses by function, such as production, administration, sales, R&D, and so on. In the GL account master and the cost center master, functional areas can be assigned.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** لإثراء الإجابة: اذكر أن الهدف الأساسي من **Functional Area** هو إعداد قائمة الدخل بطريقة **تكلفة المبيعات (Cost of Sales Accounting - COS)**، ويمكن اشتقاقها أيضاً عبر قواعد الإحلال (Substitution Rules) أو من نوع الأمر الداخلي/مركز التكلفة.

### 🔹 #18. What is Parallel Ledger Concept?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #18:** What is Parallel Ledger Concept?
> **Answer:** In New GL, SAP introduced the Parallel Ledger Concept. Parallel accounting can be conducted in General Ledger accounting by running many parallel ledgers (general ledgers) for distinct accounting principles. Data can be posted to all ledgers, a specific selection of ledgers (via ledger group), or a single ledger during posting (ledger group containing a single ledger). Depending on the requirements, there may be only one leading ledger but multiple non-leading ledgers. The non-leading ledgers are parallel ledgers that are alongside the leading ledger.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة شاملة وممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة قوية جداً. كإضافة لمستوى S/4HANA: يُرمز للـ Leading Ledger عادة بـ **`0L`**، وبجانب الـ Non-Leading Standard Ledgers، قدمت S/4HANA مفهوم **Extension Ledgers** (دفاتر الامتداد) التي تبنى فوق دفتر أساسي وتخزن فقط القيود الفارقة (Delta Postings) لتقليل حجم البيانات.

### 🔹 #19. What is a Fiscal Year Variant?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #19:** What is a Fiscal Year Variant?
> **Answer:** Fiscal Year Variant denotes the Accounting Period for which Financial Reporting is required by law to be disclosed. It is typically a twelve-month period during which a corporation generates financial statements and examines inventories on a regular basis.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3/5 — تعريف محاسبي عام ينقصه تفاصيل SAP التقنية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في SAP، الـ **Fiscal Year Variant (`OB29`)** يحدد عدد **الفترات المحاسبية العادية (Normal Posting Periods - عادة 12)** وعدد **الفترات الخاصة للتسويات (Special Periods - حتى 4 فترات، من 13 إلى 16)**. وينقسم إلى:
> - **Year-Independent:** مثل `K4` (سنة ميلادية من يناير لديسمبر) أو `V3` (أبريل لمارس).
> - **Year-Dependent:** عندما تختلف تواريخ بداية/نهاية الشهور من سنة لأخرى.

### 🔹 #20. What is a Short End Fiscal Year in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #20:** What is a Short End Fiscal Year in SAP?
> **Answer:** A short-end fiscal year occurs when a standard fiscal year is converted to a non-calendar fiscal year or vice versa. This form of shift occurs when a business joins a new co-corporate group.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — صحيحة (مع تصحيح المصطلح إلى Shortened Fiscal Year)`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** المصطلح الرسمي في SAP هو **Shortened Fiscal Year** (السنة المالية القصيرة) وليس Short End. تحتوي على عدد فترات أقل من 12 شهراً وتكون دائماً **Year-Dependent**، وتحتاج إلى إعادة احتساب للإهلاك في موديول الأصول الثابتة.

### 🔹 #21. What is Posting Period Variant?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #21:** What is Posting Period Variant?
> **Answer:** In the Fiscal Year Variant, Posting Period Variants are defined for the opening and closure of periods. You have the ability to open and close these posting periods. As many posting periods as needed can be opened at the same time.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — جيدة ولكن تنقصها الأكواد وتفاصيل التحكم`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يتم تعريف **Posting Period Variant (PPV)** عبر **`OBBO`**، وربطه بالشركة عبر **`OBBP`**، وفتح/إغلاق الفترات عبر **`OB52`**. يتيح `OB52` التحكم في الفترات حسب نوع الحساب (`+` للكل، `A` للأصول، `D` للعملاء، `K` للموردين، `M` للمواد، `S` لحسابات الأستاذ العام) ويدعم ثلاث فترات زمنية (Period 1 للترحيل العادي، Period 2 للفترات الخاصة، و Period 3 لتكامل CO/FI).

### 🔹 #22. What is a Field status Variant?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #22:** What is a Field status Variant?
> **Answer:** A Field Status Variant must be defined and assigned to the Company Code. Various field status groups are used in the field status variant to specify the field requirement (required, optional, or hidden) for each GL account at the time of posting. In the G/L account master record, the field status group is assigned to individual G/L accounts.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرّف عبر **`OBC4`** وتُربط بالشركة عبر **`OBC5`**. يُطلق على الحالات الثلاث رسمياً في SAP: **Suppress** (مخفي)، **Required Entry** (إجباري)، و **Optional Entry** (اختياري)، وتُربط بحساب الأستاذ في شاشة `FS00` (تبويب Create/bank/interest).

### 🔹 #23. What is Document Type?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #23:** What is Document Type?
> **Answer:** The document type is used to record various types of transactions in the system. Document types are applicable to all clients. For each document type, we define a number range key.
> For example, AA-Asset Posting, AF-Depreciation Posting, DZ-Customer Payment, KZ-Vendor Payment, SA-G/L Account Document, and so on.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة ومدعمة بأمثلة عملية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إلى جانب تحديد نطاق الأرقام (**Number Range**)، يتحكم **Document Type (`OBA7`)** في: نوع مستند العكس (Reverse Document Type)، وأنواع الحسابات المسموح بالترحيل عليها (A, D, K, M, S)، وما إذا كان رقم المرجع (Reference Number) أو نص رأس المستند إجبارياً.

### 🔹 #24. How many currencies can be configured for a Company Code?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #24:** How many currencies can be configured for a Company Code?
> **Answer:** A Company code can be configured to use one of three currencies: one local currency and two parallel currencies.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — دقيقة في ECC ولكن زادت في S/4HANA`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في **SAP ECC (`OB22`)**، الحد الأقصى هو **3 عملات** (عملة محلية `10` + عملتين موازيتين مثل عملة المجموعة `30` أو العملة الصعبة `40`). أما في **SAP S/4HANA (`FINSC_LEDGER`)**، يمكن تهيئة حتى **10 عملات متوازية** لكل Ledger في جدول `ACDOCA` (عملتان ثابتتان: Transaction Currency و Company Code Currency + حتى 8 عملات حرة المعرفة Freely Defined Currencies).

### 🔹 #25. What is Local Currency?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #25:** What is Local Currency?
> **Answer:** The currency entered during the company code creation process is referred to as local currency.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — صحيحة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرف أيضاً بـ **Company Code Currency** ويرمز لنوعها بالرقم **`10`**، وهي العملة القانونية لإعداد القوائم المالية المحلية للشركة.

### 🔹 #26. What is Parallel Currency?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #26:** What is Parallel Currency?
> **Answer:** The currency entered during the company code creation process is referred to as local currency, while the other two additional currencies are referred to as parallel currencies.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — صحيحة ولكن يُفضل ذكر أنواعها القياسية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** أشهر أنواع العملات الموازية في SAP هي:
> - **`30` Group Currency:** عملة المجموعة (تُؤخذ من تعريف الـ Client في `SCC4`).
> - **`40` Hard Currency:** العملة الصعبة (تُستخدم في الدول ذات التضخم المرتفع وتُعرف في `OY01`).
> - **`50` Index-Based Currency:** العملة المبنية على مؤشر.
> - **`60` Global Company Currency:** عملة الشركة العالمية.

### 🔹 #27. What is the use of Parallel Currency in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #27:** What is the use of Parallel Currency in SAP?
> **Answer:** In foreign business transactions, parallel currencies might be used. Parallel currency can be used to conduct international transactions.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🔴 2.5/5 — إجابة غير دقيقة وتخلط بين عملة المعاملة والعملة الموازية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **تصحيح مهم:** لإجراء معاملة بعملة أجنبية يكفي استخدام **Document/Transaction Currency (`00`)** ولا يشترط وجود Parallel Currency. الهدف الحقيقي من **Parallel Currency** هو تسجيل وتقييم نفس القيد المحاسبي في الوقت الفعلي بأكثر من عملة تقييم لإعداد **القوائم المالية المجمعة للمجموعة (Group Consolidation)** والتقارير متعددة الجنسيات دون الحاجة لإعادة ترجمة كل قيد يدوياً.

### 🔹 #28. What is Posting Key?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #28:** What is Posting Key?
> **Answer:** A posting key is a two-digit numerical value is used to determine the transaction type that is entered in the line item.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — مختصرة جداً وتغفل أهم وظائف مفتاح الترحيل`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في المقابلات، يجب ذكر أن **Posting Key (`OB41`)** على مستوى البند (Line Item) يتحكم في 5 عناصر أساسية:
> 1. **الجانب المحاسبي:** مدين (Debit) أم دائن (Credit).
> 2. **نوع الحساب المسموح:** (G/L, Customer, Vendor, Asset, Material).
> 3. **حالة حقول شاشة الإدخال (Field Status)** للبند.
> 4. ما إذا كان القيد يخص مبيعات أو مشتريات أو معاملة **Special G/L**.
> - *أمثلة شهيرة:* حسابات الأستاذ (`40` مدين / `50` دائن)، العملاء (`01` مدين / `15` دائن)، الموردين (`25` مدين / `31` دائن)، الأصول (`70` مدين / `75` دائن).

### 🔹 #29. What are SAP Validations and Substitutions?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #29:** What are SAP Validations and Substitutions?
> **Answer:** Validation or substitution is defined at the document and line item level for each functional area in SAP, such as Assets, Controlling, and so on.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3/5 — لا توضح الفرق بين Validation و Substitution`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يجب توضيح الفرق الجوهري:
> - **Validation (`OB28` / `GGB0`):** التحقق من صحة البيانات قبل الترحيل بناءً على شرط (Prerequisite + Check)، وإذا فشل الشرط يظهر النظام رسالة (خطأ Error يمنع الترحيل، أو تحذير Warning).
> - **Substitution (`OBBH` / `GGB1`):** استبدال أو ملء قيمة حقل تلقائياً إذا تحقق شرط معين.
> كلاهما يعمل على 3 مستويات (Callup Points): **1- Document Header**، **2- Line Item**، **3- Complete Document**.

### 🔹 #30. What is a Chart of Accounts?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #30:** What is a Chart of Accounts?
> **Answer:** A chart of accounts is a list of all GL Accounts that can be used in an accounting system that adheres to a single Accounting Principle. Every Accounting Principle requires the creation of a new Chart of Accounts.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🔴 2.5/5 — الجملة الأخيرة غير دقيقة تقنياً في SAP`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **تصحيح تقني مهم:** لا يتطلب كل مبدأ محاسبي إنشاء Chart of Accounts جديد! يمكن استخدام نفس الـ **Operating Chart of Accounts** لجميع المبادئ المحاسبية مع استخدام **Parallel Ledgers** أو حسابات تسوية. وفي SAP توجد **3 أنواع** من دليل الحسابات (`OB13`):
> 1. **Operating COA:** إجباري ويُستخدم للترحيل اليومي في FI و CO.
> 2. **Group COA:** اختياري لتوحيد الحسابات على مستوى المجموعة.
> 3. **Country-Specific (Alternative) COA:** اختياري لتلبية المتطلبات القانونية المحلية للدولة.

### 🔹 #31. What is the Financial Statement Version (FSV) in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #31:** What is the Financial Statement Version (FSV) in SAP?
> **Answer:** The Financial Statement Version (FSV) is a hierarchical arrangement of general ledger (G/L) accounts. The accounts can be set up in accordance with the legal regulations that are used to generate your financial statements. Alternatively, you can arrange the accounts according to your needs.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة دقيقة وواضحة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرّف عبر **`OB58`** (أو تطبيق Fiori *Manage Global Hierarchies* في S/4HANA) وتُستخدم لتشغيل تقارير الميزانية وقائمة الدخل مثل **`F.01`**، ويمكن إنشاء أكثر من FSV لخدمة متطلبات تقارير مختلفة (مثل واحد للإدارة الداخلية وآخر للمراجع الخارجي).

### 🔹 #32. What are Sales Tax and purchase Tax in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #32:** What are Sales Tax and purchase Tax in SAP?
> **Answer:** Purchase Tax (Input Tax) is imposed on all types of purchases, while Sales Tax (Output Tax) is imposed on all types of sales. Every country has its own sales tax and purchases tax system.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — صحيحة ولكن ينقصها كيفية الإعداد في SAP`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في SAP، يتم إدارة الضرائب عبر **Tax Calculation Procedure (`OBYZ`)** المربوط بالدولة (`OBBG`)، ويتم تعريف **أكواد الضرائب (Tax Codes - `FTXP`)** وتحديد حسابات الأستاذ للضرائب تلقائياً عبر **`OB40`**.

### 🔹 #33. What are Recurring Entries?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #33:** What are Recurring Entries?
> **Answer:** Recurring Documents are used to process transactions that are routine and repetitive in nature.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — مختصرة جداً وتحتاج إلى تفاصيل التنفيذ`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُستخدم للقيود الدورية الثابتة في المبلغ والحسابات (مثل الإيجار أو التأمين الشهري). يتم إنشاء المستند المرجعي عبر **`FBD1`** (الذي لا يؤثر مالياً بحد ذاته)، ثم يتم تنفيذ الترحيل الدوري الفعلي عبر برنامج الدفعات **`F.14`** باستخدام نطاق الأرقام **`X1`**.

### 🔹 #34. What is Accrual or Deferral Entries?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #34:** What is Accrual or Deferral Entries?
> **Answer:** In the case of recording provisions, accrual or deferral entries are a useful feature. Provisions can be created at the end of the month and reversed the following month by running a program in SAP. This feature is useful for posting accruals, deferrals, and provisional entries at the end of the month.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — جيدة جداً`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** توضيح سريع للمقابلة: **Accrual (المستحقات)** هي مصروفات أو إيرادات تخص الفترة الحالية ولكن لم تصدر/ترد فاتورتها بعد (يتم إثباتها في نهاية الشهر وعكسها أول الشهر التالي)، بينما **Deferral (المقدمات)** هي مبالغ دُفعت أو حُصلت مقدماً وتُوزع على الفترات المستفيدة.

### 🔹 #35. What is the Process of Accrual or Deferral Entries in the System?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #35:** What is the Process of Accrual or Deferral Entries in the System?
> **Answer:** There are two steps in the process:
> 1. T-Code FBS1 is used for the initial posting, in which the user posts the document while also mentioning the reversal date and reason.
> 2. T-Code F.81 is used to reverse all documents.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — دقيقة وعملية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** ممتازة. في **SAP S/4HANA**، بالإضافة إلى `FBS1` و `F.81`، أضافت SAP محرك الاستحقاق المتقدم **SAP S/4HANA Accrual Engine (`ACACACT`)** لأتمتة حساب وترحيل المستحقات الدورية لأوامر الشراء والعقود.

### 🔹 #36. What are the Year-end Activities in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #36:** What are the Year-end Activities in SAP?
> **Answer:** The followings are the year-end activities in Sap:
> - Carry Forward AR/AP Balances
> - Carry Forward GL Balances
> - Asset Fiscal Year Change
> - Asset Year-End Closing
> - Create Number Range for the Fiscal Year

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة، ويفضل إقران كل خطوة بـ T-Code الخاص بها`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إليك الأكواد المقابلة في **ECC** مقابل **S/4HANA** لإبهار المحاور:
> - ترحيل أرصدة العملاء والموردين: **`F.07`**
> - ترحيل أرصدة الأستاذ العام: **`FAGLGVTR`**
> - إعادة تقييم العملات الأجنبية: **`FAGL_FC_VAL`** (أو `FAGL_FCV` في S/4HANA)
> - تسوية حسابات GR/IR: **`F.19`**
> - فتح السنة الجديدة للأصول وإغلاق القديمة: في ECC كان يتم عبر `AJRW` ثم `AJAB`، وفي **S/4HANA (New Asset Accounting)** يتم عبر **`FAA_CMP`** و **`AJAB`**.

## 🤝 القسم الثالث: حسابات الموردين والعملاء (Accounts Payable & Accounts Receivable)
*يتناول إدارة الحسابات المساعدة للموردين (FI-AP) والعملاء (FI-AR)، حسابات التسوية (Reconciliation Accounts)، شروط الدفع، مؤشرات الأستاذ العام الخاصة (Special G/L)، والمطالبات المالية (Dunning).*

### 🔹 #37. What is Vendor Account Group?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #37:** What is Vendor Account Group?
> **Answer:** A Vendor group is an object that was created to differentiate between different types of Vendors and to group Vendors of a similar nature transactionally.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — جيدة ولكن اذكر وظائف التحكم التقنية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرّف عبر **`OBD3`** (مثل: موردين محليين، موردين أجانب، موردين لمرة واحدة One-time Vendors)، وتتحكم في: **Number Range**، و **Field Status** لشاشات بيانات المورد، وما إذا كان الحساب **One-Time Account**. وفي **S/4HANA** تقابلها **BP Grouping**.

### 🔹 #38. What is Vendor Reconciliation Account?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #38:** What is Vendor Reconciliation Account?
> **Answer:** All vendors are assigned to a general ledger account known as the vendor reconciliation Account. Vendor balances are automatically reconciled with the vendor reconciliation account balance.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** هو حساب أستاذ عام (ميزانية - التزامات) يربط الأستاذ المساعد للموردين (AP Sub-ledger) بالأستاذ العام (General Ledger) لحظياً، ولا يُسمح بالترحيل اليدوي المباشر عليه أبداً.

### 🔹 #39. What are Payment Terms?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #39:** What are Payment Terms?
> **Answer:** A Payment Term specifies the conditions under which a payment must be made. It symbolizes the typical agreements you have with your vendors and customers. When a vendor or customer’s Master Record is created, a payment Term is assigned to them.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرّف عبر **`OBB8`** وتحدد 3 عناصر رئيسية لحساب تاريخ الاستحقاق والخصم: **Baseline Date** (تاريخ الأساس لحساب الاستحقاق)، **Cash Discount Percentages** (نسب الخصم النقدي للتعجيل بالدفع)، و **Due Date / Grace Periods** (مدد السماح).

### 🔹 #40. What is Security Money Deduction from Bill?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #40:** What is Security Money Deduction from Bill?
> **Answer:** The security money is deducted from the bill during the payment process. In this process, a certain amount is deducted from the final payment to the vendor as a security deposit and is returned after a certain period of time, depending on the business terms and conditions. This will be kept as a separate GL liability owed to the vendor.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — صحيحة وتُعرف أيضاً بـ Retention Money (تأمين ضمان الأعمال)`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُدار هذا المبلغ في SAP باستخدام **Special G/L Indicator** (مثل `H` للـ Retention) بحيث يظهر في حساب تسوية بديل (Alternative Reconciliation Account) منفصل عن المديونية التجارية العادية للمورد.

### 🔹 #41. What is Customer Account Group?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #41:** What is Customer Account Group?
> **Answer:** A customer group is an object that was created to differentiate between different types of customers and to group customers of similar nature in terms of transactions.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — جيدة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرّف عبر **`OBD2`** وتتحكم في نطاق الأرقام (Number Range) وحالة الحقول (Field Status) ونوع العميل (عادي أم One-time Customer)، وتم دمجها في **S/4HANA** ضمن إعدادات **Business Partner (BP)**.

### 🔹 #42. What is a Customer Reconciliation Account?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #42:** What is a Customer Reconciliation Account?
> **Answer:** A customer reconciliation account is a general ledger account that is permanently reconciled in SAP with the customer balance. When a financial posting is made to a customer account, the same posting is automatically replicated in the customer’s reconciliation account in the general ledger. Customer reconciliation accounts can only be posted through the customer route and cannot be directly posted to in the general ledger.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة نموذجية وكاملة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة ممتازة ومكتملة الأركان. يتم ربط هذا الحساب في بيانات العميل الرئيسية على مستوى الشركة (Company Code Data) ويتم تفعيل خيار `Recon. account for acct type: Customers (D)` في شاشة حساب الأستاذ `FS00`.

### 🔹 #43. What is Special GL Indicator?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #43:** What is Special GL Indicator?
> **Answer:** Special GL indicators are those that are used in transactions other than regular accounts receivable and payable transactions to identify a special GL transaction.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — صحيحة ولكن تحتاج أمثلة وتوضيح آلية عملها`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يستخدم **Special G/L Indicator (`FBKP`)** لتوجيه معاملات خاصة للعملاء أو الموردين إلى **Alternative Reconciliation Account** بدلاً من حساب التسوية العادي حتى لا تختلط بالذمم التجارية العادية في الميزانية. من أهم أمثلته: **`A`** للدفعات المقدمة (Down Payments)، **`F`** لطلب دفعة مقدمة (Noted Item - بند تذكيري بسطر واحد لا يؤثر محاسبياً)، و **`G`** لخطابات الضمان.

### 🔹 #44. What is Day Sales Outstanding (DSO)?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #44:** What is Day Sales Outstanding (DSO)?
> **Answer:** Days Sales Outstanding represents the average number of days it takes for a receivable to be paid by the customer or the average collection period for the company. The number of days’ sales outstanding (DSO) is used to assess the effectiveness of receivable management.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يمكن إضافة المعادلة المالية لإثراء الإجابة: `DSO = (Accounts Receivable / Total Credit Sales) × Number of Days`. في S/4HANA توجد تطبيقات Fiori تحليلية جاهزة لقياس الـ DSO لحظياً.

### 🔹 #45. What is Dunning in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #45:** What is Dunning in SAP?
> **Answer:** Dunning’ is the process of sending payment chasing letters to consumers. We can determine which letter has been issued to the client by using the dunning level on the customer master.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — جيدة ولكن اذكر خطوات التهيئة والتشغيل`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يتم إعداد **Dunning Procedure** عبر **`FBMP`** (حيث نحدد Dunning Interval، عدد مستويات المطالبة Dunning Levels حتى 9 مستويات، فترة السماح، والحد الأدنى للمبالغ والمصروفات)، ويتم تشغيل برنامج المطالبات عبر **`F150`**.

## 🏦 القسم الرابع: محاسبة الأصول الثابتة والبنوك والمدفوعات (Asset & Bank Accounting)
*يستعرض دورة حياة الأصول الثابتة (FI-AA)، دليل ومناطق ومفاتيح الإهلاك، عقود الإيجار، صندوق المصروفات النثرية (Cash Journal)، برنامج الدفع التلقائي (`F110`)، وحساب وسيط استلام البضاعة/الفواتير (GR/IR).*

### 🔹 #46. What is the Chart of Depreciation Accounts?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #46:** What is the Chart of Depreciation Accounts?
> **Answer:** A depreciation chart is used to manage asset valuation for various legal requirements. Every Company Code that uses Assets Accounting must be assigned to a Chart of depreciation.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُعرف رسمياً بـ **Chart of Depreciation (`EC08`)** وهو خاص بكل دولة (Country-specific) ويحتوي على قائمة بـ **Depreciation Areas** (مناطق الإهلاك)، ويتم ربطه بالـ Company Code عبر **`OAOB`**.

### 🔹 #47. What is the Depreciation Area?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #47:** What is the Depreciation Area?
> **Answer:** The depreciation area aids in valuing asset balances and transactions for various purposes. It enters and depreciates values into the general ledger.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — جيدة ولكن وضح أنواع التقييم المتوازي`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُستخدم **Depreciation Areas** لتقييم نفس الأصل الثابت لأغراض مختلفة بالتوازي: مثلاً المنطقة **`01` Book Depreciation** (للإهلاك المحاسبي الرئيسي الذي يُرحل لحظياً للأستاذ العام)، ومنطقة للإهلاك الضريبي (**Tax Depreciation**)، ومنطقة للمحاسبة الإدارية (**Cost-Accounting Depreciation**).

### 🔹 #48. What is Asset Class?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #48:** What is Asset Class?
> **Answer:** Fixed assets are classified into asset classes (e.g., vehicles, furniture, machines). Asset classes are used to categorize fixed assets based on business and legal requirements. The asset class is divided into two sections: master data and depreciation area.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** لتقوية الإجابة تقنياً: يُعرّف **Asset Class (`OAOA`)** على مستوى الـ Client، ويحتوي على 3 عناصر تحكم رئيسية: **Account Determination** (مفتاح تحديد حسابات الأستاذ)، **Screen Layout Rule** (شكل شاشة البيانات الرئيسية)، و **Number Range Interval** (نطاق أرقام الأصول).

### 🔹 #49. What is Depreciation Key?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #49:** What is Depreciation Key?
> **Answer:** The depreciation key (valuation key) controls the asset’s valuation in specific depreciation areas.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — مختصرة جداً وتغفل مكونات مفتاح الإهلاك`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُعرّف **Depreciation Key (`AFAMA`)** ويحدد كيفية حساب الإهلاك تلقائياً من خلال 5 طرق داخلية (Calculation Methods): **Base Method**، **Declining-Balance Method**، **Maximum Amount Method**، **Multi-Level Method** (النسب)، و **Period Control Method** (تحديد متى يبدأ وينتهي الإهلاك عند الإضافة أو الاستبعاد).

### 🔹 #50. What is Account Determination?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #50:** What is Account Determination?
> **Answer:** Account determinations are the keys in SAP that are used to link asset classes or master records to general ledger (G/L) accounts based on the nature of the transaction.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة دقيقة وواضحة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يتم إعداد ربط الحسابات لمفتاح **Account Determination** عبر **`AO90`** (حيث نربط حسابات التكلفة، مجمع الإهلاك، مصروف الإهلاك، وأرباح/خسائر بيع أو تكهين الأصول).

### 🔹 #51. What is Financial Lease Asset?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #51:** What is Financial Lease Asset?
> **Answer:** Financial lease asset terms operate in the same way as company-owned assets, with an acquisition cost and normal depreciation. Leased assets will be created as a separate asset class where lease-related data for the asset can be maintained.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — صحيحة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُرسمل (Capitalized) عقود التأجير التمويلي في الميزانية وتُستهلك على مدار عمر الأصل أو مدة العقد. وفي الأنظمة الحديثة المطبقة لمعيار **IFRS 16 / ASC 842**، تُدار عقود الإيجار وحسابات **Right-of-Use (RoU) Assets** عبر موديول **SAP RE-FX (Flexible Real Estate Management)** المتكامل مع FI-AA.

### 🔹 #52. What is Operating Lease Asset?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #52:** What is Operating Lease Asset?
> **Answer:** Operating lease assets are not shown on the balance sheet. As a result, for reporting and tracking purposes, a zero value asset will be created in the appropriate asset class, and an evaluation group key will be entered in the Evaluation Group 1 field in the Allocations tab of the asset master.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — تعكس الممارسة القديمة قبل معيار IFRS 16`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الإجابة تصف المعالجة التقليدية حيث لم تكن عقود الإيجار التشغيلي تُرسمل في الميزانية. **ملاحظة مهمة للمقابلات:** بعد تطبيق معيار **IFRS 16**، أصبح المستأجر (Lessee) ملزماً برسملة معظم عقود الإيجار في الميزانية كأصول حق استخدام (**RoU Assets**) باستثناء العقود قصيرة الأجل (أقل من 12 شهراً) أو منخفضة القيمة.

### 🔹 #53. What is Cash Journal?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #53:** What is Cash Journal?
> **Answer:** Bank Accounting includes the Cash Journal as a sub-module. It is used to manage the cash and petty cash transactions of a business. The system computes and displays the opening and closing balances, as well as the receipts and payments totals, automatically. For a single company code, many cash journals can be created.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة وافية وممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة ممتازة. أضف فقط الأكواد الخاصة بصندوق المصروفات النثرية (Petty Cash): التهيئة عبر **`FBCJC0`**، وإدخال حركات القبض والصرف اليومية عبر **`FBCJ`**.

### 🔹 #54. What is a Bank key?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #54:** What is a Bank key?
> **Answer:** Each bank branch must have its own bank key (account number). This includes the bank’s name, address, swift code, branch code, and tax identification number.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — تحتوي على خلط بسيط بين Bank Key و Account Number`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **تصحيح مهم:** الـ **Bank Key (`FI01`)** هو الكود التعريفي لفرع البنك نفسه على مستوى الـ Client (مثل Routing Number أو كود الفرع) **وليس رقم الحساب البنكي للشركة (Bank Account Number)**. أما حساب الشركة البنكي فيُعرّف داخل **House Bank (`FI12` أو تطبيق Fiori *Manage Bank Accounts* في S/4HANA)** تحت Account ID.

### 🔹 #55. What are the Different Procedures for Paying Vendor Invoices?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #55:** What are the Different Procedures for Paying Vendor Invoices?
> **Answer:** The different procedures for paying vendor invoices are as follows:
> - Manual Payment
> - Automatic payment (Cheques, Wire transfer, etc.)

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — صحيحة ومباشرة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** اذكر أكواد المعاملات (T-Codes) لكل طريقة:
> - **الدفع اليدوي (Manual Outgoing Payment):** عبر **`F-53`** (أو **`F-58`** للدفع مع طباعة شيك).
> - **الدفع التلقائي (Automatic Payment Program - APP):** عبر **`F110`**.

### 🔹 #56. What is Automatic Payment in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #56:** What is Automatic Payment in SAP?
> **Answer:** Automatic payment is a system in which SAP can automate payments to vendors and customers based on a due date computed from payment terms and the baseline date.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — جيدة ولكن سؤال `F110` في المقابلات يتطلب ذكر خطوات التهيئة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** برنامج الدفع التلقائي (**APP - `F110`**) يُعدّ في **`FBZP`** عبر 6 أزرار شهيرة تُسأل في كل مقابلة:
> 1. **All Company Codes** (العلاقات بين الشركات والخصم النقدي)
> 2. **Paying Company Codes** (الحد الأدنى للمدفوعات والنماذج)
> 3. **Payment Methods in Country** (طرق الدفع على مستوى الدولة)
> 4. **Payment Methods in Company Code** (حدود المبالغ وتفاصيل الشركة)
> 5. **Bank Determination** (ترتيب أولوية البنوك Ranking Order والحسابات)
> 6. **House Banks** (بنوك الشركة).

### 🔹 #57. What Level does SAP Store Customer and Vendor Codes?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #57:** What Level does SAP Store Customer and Vendor Codes?
> **Answer:** SAP saves the Vendor and Customer codes at the client level. That is, by expanding the company code view, any company code can use the customer and vendor codes.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** لتفصيل الهيكل التقني لبيانات العملاء والموردين (و **Business Partner - `BP`** في S/4HANA)، فهي تُخزن على **3 مستويات**:
> 1. **General Data (Client Level):** الاسم، العنوان، البيانات البنكية (جداول `KNA1` / `LFA1` / `BUT000`).
> 2. **Company Code Data:** حساب التسوية، شروط الدفع (`KNB1` / `LFB1`).
> 3. **Sales Area / Purchasing Org Data:** بيانات المبيعات (`KNVV`) أو المشتريات (`LFM1`).

### 🔹 #58. What is GRIR Clearing Account in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #58:** What is GRIR Clearing Account in SAP?
> **Answer:** In SAP, the GR IR Clearing Account is a clearing account that acts as an intermediate for goods and invoices in transit. It stands for the accounts of Goods Receipt and Invoice Receipt. It is a balance sheet account.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** توضيح القيود المحاسبية يعطي انطباعاً قوياً في المقابلة:
> - عند **استلام البضاعة (`MIGO`)**: من ح/ المخزون (`BSX`) إلى ح/ وسيط استلام بضاعة/فواتير **GR/IR (`WRX`)**.
> - عند **استلام الفاتورة (`MIRO`)**: من ح/ وسيط **GR/IR (`WRX`)** إلى ح/ المورد.
> ويتم تسوية الأرصدة تلقائياً عبر **`F.13`**، وإعادة تبويب الفروق في نهاية الفترة عبر **`F.19`**.

## ⚙️ القسم الخامس: المحاسبة الإدارية ومراكز التكلفة والأوامر الداخلية (Overhead Cost Controlling)
*يشرح بنية موديول الرقابة (SAP CO)، التكامل اللحظي بين FI و CO، مراكز الربحية (Profit Centers)، مراكز التكلفة (Cost Centers)، الأوامر الداخلية الحقيقية والإحصائية (Internal Orders)، ومحاسبة عناصر التكلفة.*

### 🔹 #59. What is the Controlling Module of SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #59:** What is the Controlling Module of SAP?
> **Answer:** SAP’s controlling module provides management with the information they need to make decisions. It enables the organization’s numerous processes to be coordinated, monitored, and optimized.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يركز **SAP CO** على التخطيط، الرقابة، وتوجيه التكاليف الداخلية ومقارنة التكاليف الفعلية بالمخططة (Actual vs. Plan Variance Analysis) لدعم قرارات الإدارة الداخلية.

### 🔹 #60. What is the Relationship Between FI and CO?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #60:** What is the Relationship Between FI and CO?
> **Answer:** In the SAP system, Controlling (CO) and Financial Accounting (FI) are separate components. The necessary FI accounts are controlled as cost/revenue items in CO. The user must designate a cost object, such as cost centers, projects or orders, COPA segment, etc., to the costs and revenues posted in FI. The item flows from FI to CO due to the combination of cost element and cost object. The data transfer between the two components occurs in real-time.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة (مع إضافة تحديث S/4HANA الجوهري)`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الإجابة تشرح التدفق اللحظي بدقة. **تحديث S/4HANA بالغ الأهمية للمقابلات:** في S/4HANA تم دمج حسابات الأستاذ وعناصر التكلفة (Cost Elements) في شاشة واحدة هي **`FS00`**، وتُحفظ قيود FI و CO معاً في نفس اللحظة داخل جدول **`ACDOCA` (Universal Journal)**، مما ألغى الحاجة لمطابقة FI مع CO في نهاية الشهر.

### 🔹 #61. What are the Components of Controlling?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #61:** What are the Components of Controlling?
> **Answer:** Controlling has various sub-components, some of which are as follows:
> - Cost Element Accounting
> - Cost Center Accounting
> - Internal Orders
> - Product Cost Controlling
> - Profitability Analysis
> - Planning & Budgeting

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الاختصارات التقنية المقابلة لها في SAP هي: **CO-OM-CEL** (Cost Element Accounting)، **CO-OM-CCA** (Cost Center Accounting)، **CO-OM-OPA** (Internal Orders)، **CO-PC** (Product Cost Controlling)، **CO-PA** (Profitability Analysis)، بالإضافة إلى **EC-PCA / Profit Center Accounting**.

### 🔹 #62. What is Profit Center?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #62:** What is Profit Center?
> **Answer:** A profit center is an accounting organizational unit that often reflects the organization’s management-oriented structure for the purposes of internal control. A profit center is where revenue and costs are recorded.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُنشأ عبر **`KE51`**، ومع تفعيل **New GL / S/4HANA Document Splitting**، يمكن استخراج ميزانية عمومية كاملة (Balance Sheet) بجانب قائمة الدخل (P&L) على مستوى كل **Profit Center**، مما يجعله يعمل كـ "شركة داخل الشركة".

### 🔹 #63. What is Cost Center?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #63:** What is Cost Center?
> **Answer:** A cost center is an organizational unit in the Controlling Area that does not generate direct profit but collects the costs of running a business.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — دقيقة وواضحة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُنشأ عبر **`KS01`** ويُمثل مكان حدوث التكلفة (مثل قسم الصيانة، الموارد البشرية، أو خط إنتاج)، ويُربط بـ **Profit Center** داخل بياناته الرئيسية حتى تتدفق التكاليف تلقائياً إلى مركز الربحية المقابل.

### 🔹 #64. What is an Internal Order?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #64:** What is an Internal Order?
> **Answer:** Internal Order is a cost object in which we book our costs for a certain time period. An Internal Order is an incredibly versatile CO tool that may be used to track expenditures and, in some situations profits within a controlling area.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُنشأ عبر **`KO01`** ويُستخدم غالباً لمراقبة تكاليف أنشطة أو مشاريع مؤقتة ذات ميزانية محددة (مثل معرض تسويقي، حملة إعلانية، صيانة طارئة، أو أصل تحت الإنشاء) مع إمكانية تفعيل رقابة الموازنة (**Availability Control - `KO22`**).

### 🔹 #65. What are the Types of Internal Order?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #65:** What are the Types of Internal Order?
> **Answer:** There are Two Types of Internal order, which are as follows:
> - Real Internal Order
> - Statistical Internal Order

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — صحيحة من حيث طبيعة الترحيل`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إلى جانب تقسيمها إلى **Real** و **Statistical**، تُصنف وظيفياً أيضاً إلى 4 فئات: **Overhead Orders** (أوامر المصروفات العامة)، **Investment Orders** (أوامر الاستثمار/الأصول تحت الإنشاء AuC)، **Accrual Orders** (أوامر الاستحقاق)، و **Orders with Revenues**.

### 🔹 #66. What is Real Internal Order?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #66:** What is Real Internal Order?
> **Answer:** Real internal orders are cost objects capable of collecting expenses that may then be settled to various objects such as cost centers, fixed assets, and so on.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تستقبل تكاليف حقيقية، وفي نهاية الفترة يجب تسويتها (**Settlement - `KO88`**) لتفريغ رصيدها إلى المستلم النهائي (Settlement Receiver مثل Cost Center أو Asset أو G/L Account أو Profitability Segment) وفقاً لـ **Settlement Profile**.

### 🔹 #67. What is the Primary Purpose of Real Internal Order?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #67:** What is the Primary Purpose of Real Internal Order?
> **Answer:** Real internal orders will mostly be used primarily for asset-related transactions.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3/5 — إجابة ضيقة جداً وتحصر الاستخدام في حالة واحدة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **تصحيح وتوسيع:** الأوامر الداخلية الحقيقية لا تقتصر فقط على الأصول (Investment Orders / AuC)، بل تُستخدم على نطاق واسع لتتبع ومراقبة ميزانيات **الحملات التسويقية، الفعاليات المؤقتة، مشاريع البحث والتطوير الصغيرة، وأعمال الصيانة والإصلاح** ثم تسويتها إلى مراكز التكلفة أو CO-PA.

### 🔹 #68. What is Statistical Internal Order?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #68:** What is Statistical Internal Order?
> **Answer:** Statistical internal orders are statistical objects that do not gather expenses. They are only used for reporting purposes.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — تحتاج لتوضيح كيف تُرحل عليها المصروفات`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **توضيح تقني:** الأمر الإحصائي (الذي يُفعل فيه خيار `Statistical Order` في `KO01`) يجمع المصروفات **إحصائياً لأغراض التقارير فقط**، ولذلك عند الترحيل عليه يطلب النظام إجبارياً إدخال **Real Cost Object** بجانبه (مثل Cost Center) ليتحمل التكلفة الحقيقية، ولا يمكن إجراء Settlement للأمر الإحصائي.

### 🔹 #69. What is Cost Element Accounting?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #69:** What is Cost Element Accounting?
> **Answer:** Cost Elements in SAP are cost modes/carriers. Cost Element Accounting is used to manage cost elements, which are a Controlling master data object. It is the section of accounting in which costs incurred during a settlement period are entered and grouped. It is not an accounting system, but rather a detailed record of data that serves as the foundation for cost accounting.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — جيدة جداً`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُجيب عناصر التكلفة (Cost Elements) عن سؤال: **ما هي طبيعة التكلفة؟** (رواتب، كهرباء، خامات، تسويات داخلية)، وتنقسم إلى **Primary Cost Elements** و **Secondary Cost Elements**.

## 🏭 القسم السادس: تحليل الربحية وتكاليف المنتجات والتصنيع (CO-PA & Product Costing)
*يتعمق في تحليل الربحية (Costing-Based vs. Account-Based CO-PA)، عناصر التكلفة الأولية والثانوية، قوائم المواد (BOM) ومسارات التشغيل (Routing)، التكلفة المعيارية (`CK11N`/`CK40N`)، الدفتر الفعلي للمواد (Material Ledger)، والانحرافات الإنتاجية.*

### 🔹 #70. What is Product Cost Controlling?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #70:** What is Product Cost Controlling?
> **Answer:** Product Cost Controlling is a Controlling component that deals with product cost and related activities. It is a crucial component of standard costing, which entails estimating standard costs based on raw material prices, production activities, and overheads, and then recording and controlling the cost flows that occur during the manufacturing process.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** للتميز في المقابلة، اذكر أن **Product Cost Controlling (CO-PC)** ينقسم إلى 3 مكونات فرعية:
> 1. **Product Cost Planning (CO-PC-PCP):** لحساب التكلفة المعيارية للمنتج.
> 2. **Cost Object Controlling (CO-PC-OBJ):** لمتابعة التكاليف الفعلية على أوامر الإنتاج وحساب WIP والانحرافات (Variances).
> 3. **Actual Costing / Material Ledger (CO-PC-ACT):** لحساب التكلفة الفعلية الدورية للمواد.

### 🔹 #71. What is Controlling Profitability Analysis (CO-PA)?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #71:** What is Controlling Profitability Analysis (CO-PA)?
> **Answer:** Controlling Profitability Analysis (CO-PA) is a Controlling component that allows enterprises to evaluate and analyze the profitability of market segments divided by products, customers, orders, and business units (sales organizations) in relation to a company’s profit margin.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة نموذجية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة ممتازة. يساعد **CO-PA** الإدارة في تحليل **Contribution Margin** (هامش المساهمة) عبر أبعاد متعددة (Multi-dimensional reporting) للإجابة عن: من هو العميل أو المنتج أو المنطقة الأكثر ربحية؟

### 🔹 #72. What are the Two Types of COPA Analysis?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #72:** What are the Two Types of COPA Analysis?
> **Answer:** The two types of COPA analysis are as follows:
> - Costing Based COPA and
> - Account-Based COPA

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة، مع إضافة النوع الثالث المدمج في S/4HANA`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في **SAP S/4HANA**، أصبح **Account-Based CO-PA** (الذي يسمى الآن **Margin Analysis**) هو الخيار الافتراضي المدمج في جدول `ACDOCA`، كما يمكن تفعيل **Combined CO-PA** للجمع بين مزايا الطريقتين.

### 🔹 #73. What is Costing-based Profitability Analysis?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #73:** What is Costing-based Profitability Analysis?
> **Answer:** Costing-based Profitability Analysis is a type of profitability analysis that allows for the breakdown of costs and revenues to a much finer level than the GL account level. This is not automatically reconciled to the general ledger.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يعتمد **Costing-Based CO-PA** على **Value Fields** (حقول القيم) لتخزين المبالغ والكميات في جداول منفصلة (`CE1xxxx` - `CE4xxxx`)، ويتميز بقدرته على إظهار تفاصيل بنود التكلفة (Cost Component Split) والفروق التقديرية، لكنه يحتاج لمطابقة يدوية مع FI لأن التوقيت قد يختلف (مثلاً عند استلام البضاعة مقابل الفوترة).

### 🔹 #74. What is Account-based Profitability Analysis?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #74:** What is Account-based Profitability Analysis?
> **Answer:** Account-based Profitability Analysis is a type of profitability analysis that is organized in accounts and uses an account-based valuation technique. The use of cost and revenue elements distinguishes this type. It enables profitability reports that are reconciled with financial accounting.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** ممتازة. في **S/4HANA Margin Analysis (Account-based CO-PA)**، يتم تسجيل جميع الخصائص (Characteristics) مباشرة في جدول **`ACDOCA`**، كما أضافت SAP ميزة **Cost of Goods Sold (COGS) Split** و **Production Variance Split** على حسابات الأستاذ لتعويض المزايا التي كانت حصرية للـ Costing-based CO-PA.

### 🔹 #75. What is the Value Field in COPA?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #75:** What is the Value Field in COPA?
> **Answer:** In the profitability analysis, value fields are numbers or value-related fields such as quantity, sales revenue, discount value, and so on.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُستخدم **Value Fields (`KEA6`)** فقط في **Costing-Based CO-PA**، وتنقسم إلى نوعين: **Amount Fields** (لحفظ القيم المالية مثل الإيرادات والخصومات وتكلفة المبيعات) و **Quantity Fields** (لحفظ الكميات المباعة).

### 🔹 #76. What are Primary Cost Elements?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #76:** What are Primary Cost Elements?
> **Answer:** Primary Cost Elements are those cost elements whose costs originate outside of the CO module and include accrual costs utilized for controlling. In Financial Accounting, each Primary Cost element will have a matching G/L account.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تنشأ تكلفتها من معاملات مالية خارجية في FI/MM/SD ولها حساب مقابل في قائمة الدخل (P&L G/L Account). أهم فئاتها (Cost Element Categories): **`01`** للمصروفات العامة، **`11`** للإيرادات، و **`12`** لخصومات المبيعات. (في ECC كانت تُنشأ بـ `KA01`، وفي S/4HANA تُنشأ مباشرة كحسابات `FS00` من نوع *Primary Costs or Revenue*).

### 🔹 #77. What are Secondary Cost Elements?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #77:** What are Secondary Cost Elements?
> **Answer:** Secondary cost elements are cost components used to apportion costs for internal activities. In Financial Accounting, secondary cost elements do not have a corresponding G/L account. They are exclusively used in controlling and, as a result, cannot be defined as a general ledger account in Financial Accounting.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — صحيحة في ECC ولكن تغيرت جذرياً في S/4HANA`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **تنبيه جوهري لمقابلات S/4HANA:** في نظام **SAP ECC** لم يكن للـ Secondary Cost Elements حساب في `FS00` (كانت تُنشأ في CO عبر `KA06`). أما في **SAP S/4HANA**، **أصبحت Secondary Cost Elements جزءاً من دليل الحسابات وتُنشأ كحسابات أستاذ عام في `FS00`** تحت نوع الحساب **Secondary Costs**! ومن أشهر فئاتها: **`21`** (Internal Settlement)، **`42`** (Assessment)، و **`43`** (Internal Activity Allocation).

### 🔹 #78. What Are Some Uses of Secondary Cost Elements?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #78:** What Are Some Uses of Secondary Cost Elements?
> **Answer:** Some uses of secondary cost elements are as follows:
> - Activity allocation in product costing
> - COPA allocation

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4/5 — صحيحة ويمكن إضافة أهم استخداماتها الأخرى`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تشمل استخداماتها الأساسية:
> - **Internal Activity Allocation (`43`):** تحميل ساعات العمل والماكينات على أوامر الإنتاج.
> - **Assessment (`42`):** توزيع تكاليف مراكز الخدمات على مراكز الإنتاج أو CO-PA (`KSU5` / `KEU5`).
> - **Internal Order / Project Settlement (`21`):** تسوية الأوامر الداخلية والمشاريع.
> - **Overhead Calculation (`41`):** تحميل الأعباء الإضافية via Costing Sheet.

### 🔹 #79. What is Cost Center Standard Hierarchy?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #79:** What is Cost Center Standard Hierarchy?
> **Answer:** A Cost Center Standard Hierarchy is a hierarchical arrangement of all cost centers in the controlling area. A Cost Center Standard Hierarchy is an arrangement of many cost center groups, one below the other, and the groups that have been transferred to higher-level groups, all of which are part of the standard hierarchy.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُعرّف في إعدادات الـ Controlling Area (`OKKP`) وتُدار عبر **`OKEON`**، وهي شجرة إلزامية يجب أن يندرج تحتها **كل Cost Center** يتم إنشاؤه داخل الـ Controlling Area لضمان عدم سقوط أي مركز تكلفة من التقارير الإجمالية.

### 🔹 #80. What is a Bill of Material (BOM)?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #80:** What is a Bill of Material (BOM)?
> **Answer:** A bill of materials (BOM) is a formally structured list of the components used in the manufacture of a finished/semi-finished product. The list includes the material number of each component, as well as the quantity and unit of measurement.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة نموذجية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تنتمي لموديول **PP** وتُنشأ عبر **`CS01`**، وفي حساب تكلفة المنتج (**Product Costing**)، يعتمد النظام على الـ BOM لحساب **تكلفة المواد المباشرة (Direct Material Cost)** لكل منتج تام أو نصف مصنع.

### 🔹 #81. What is Routing?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #81:** What is Routing?
> **Answer:** Routings define the processes that are employed to create the final product. Routing includes the work centers and typical activities used in the material’s manufacture.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُنشأ الـ **Routing** عبر **`CA01`** (وفي الصناعات التحويلية/الكيميائية Process Manufacturing يُسمى **Master Recipe - `C201`**)، ويُستخدم في حساب التكلفة المعيارية لتحديد **تكاليف التحويل والتشغيل (Conversion / Activity Costs)** بناءً على أزمنة العمليات داخل كل **Work Center**.

### 🔹 #82. What is Activity Type?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #82:** What is Activity Type?
> **Answer:** Activity type is a Controlling component that categorizes activities performed in a cost center. In other words, activity types can be described as the cost center’s output. Setup time, machine time, labor time, and so on are examples of activity types.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُنشأ عبر **`KL01`** ويرتبط بـ **Secondary Cost Element من الفئة `43`**، ويتم تسعير ساعة النشاط (Activity Price/Rate) عبر التخطيط في **`KP26`** أو الحساب الفعلي للأسعار عبر **`KSII`**.

### 🔹 #83. What is a Maintenance Order?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #83:** What is a Maintenance Order?
> **Answer:** A maintenance order, like an internal order, is a cost object with additional functionality needed for Plant Maintenance. It records plant maintenance expenses for further processing within the Controlling module.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** ينتمي لموديول **SAP PM (Plant Maintenance)** ويُنشأ عبر **`IW31`** لتجميع تكاليف قطع الغيار والعمالة الخارجية/الداخلية لعمليات الصيانة، ثم يُسوى (Settled) عبر **`KO88`** إلى مركز التكلفة المستفيد أو الأصل الثابت.

### 🔹 #84. What is Production Order/Product Cost Collector?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #84:** What is Production Order/Product Cost Collector?
> **Answer:** A production order or product cost collector, is a cost object that, like an internal order, includes additional features that are important for Production Planning. It records production costs for further processing within the Controlling module.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — تدمج مفهومي Production Order و Product Cost Collector دون توضيح الفرق بينهما`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** **إضافة مهمة للمقابلات:**
> - **Production Order (`CO01`):** يُستخدم في بيئة التصنيع المتقطع (**Discrete Manufacturing** - Product Cost by Order) حيث يتم تتبع التكاليف لكل أمر إنتاج على حدة.
> - **Product Cost Collector (`KKF6N`):** يُستخدم في بيئة التصنيع المتكرر (**Repetitive Manufacturing** - Product Cost by Period) حيث يتم تجميع التكاليف على مستوى المنتج/خط الإنتاج لفترة زمنية كاملة بدلاً من كل أمر منفرد.

### 🔹 #85. What is the Statistical key Figure?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #85:** What is the Statistical key Figure?
> **Answer:** Statistical key figures give information on non-monetary statistics for the profit centers such as the number of personnel, machines, capacity utilization, market information, and so on.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — جيدة، مع توضيح استخدامها وأنواعها`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُنشأ **Statistical Key Figures (SKF)** عبر **`KK01`** وتُستخدم في Cost Centers و Profit Centers و Internal Orders كـ **أساس لتوزيع التكاليف (Tracing Factor / Allocation Base)** في دورات التوزيع (**Distribution** و **Assessment**) مثل المساحة بالمتر المربع لتوزيع الإيجار، أو عدد الموظفين لتوزيع تكاليف الكافيتريا. وتنقسم إلى:
> - **Fixed Values (Category 1):** تظل ثابتة طوال السنة ما لم تُعدل (مثل المساحة أو عدد الموظفين).
> - **Total Values (Category 2):** تتغير شهرياً ولا ترحل للشهر التالي (مثل عدد مكالمات الهاتف أو كيلوواط الكهرباء).

### 🔹 #86. What is Profitability Segment?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #86:** What is Profitability Segment?
> **Answer:** The profitability segment is a Profitability Analysis object to which costs and revenues are assigned.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** الـ **Profitability Segment (PSG)** هو تقاطع مجموعة من الخصائص (**Characteristics**)، على سبيل المثال: `[العميل X + المنتج Y + منطقة المبيعات Z + قناة التوزيع W]`، وهو الكائن الذي تُقاس عليه الربحية في **CO-PA**.

### 🔹 #87. What are Characteristics?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #87:** What are Characteristics?
> **Answer:** Characteristics are the criteria in Profitability Analysis (CO-PA) that can be used to examine operating performance.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — جيدة، ويفضل دعمها بأمثلة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تمثل الـ **Characteristics (`KEA5`)** أبعاد التحليل التي تجيب عن سؤال: **على أي مستوى نريد تحليل الربحية؟** مثل: Customer، Product، Sales Organization، Distribution Channel، Country، أو Brand. وتأتي إما جاهزة قياسياً (Fixed/Predefined) أو مخصصة (User-defined `WWxxx`).

### 🔹 #88. What is Standard Cost Estimate?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #88:** What is Standard Cost Estimate?
> **Answer:** Standard cost estimate is the process of calculating the predicted standard cost of an In-House manufactured product. It estimates the manufacturing cost of the finished product by taking into account the projected raw material costs and conversion expenses. It is a component of SAP’s Product Costing module.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** تُنفذ لصنف واحد عبر **`CK11N`** (وتُعتمد عبر **`CK24`**) أو لمجموعة أصناف عبر **`CK40N`**، وتُحسب بناءً على معادلة: `Standard Cost = Material Cost (from BOM) + Activity/Conversion Cost (from Routing & Work Centers) + Overhead Cost (from Costing Sheet)`.

### 🔹 #89. What is a Mixed Costing Estimate?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #89:** What is a Mixed Costing Estimate?
> **Answer:** Mixed costing can be utilized when inventory value must incorporate the mixed procurement costs when there are different procurement possibilities for the same material, such as two production lines or two vendors.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة دقيقة وواضحة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** لإعداد **Mixed Costing** في SAP: نُعرف **Procurement Alternatives (`CK91N`)** لكل بديل توريد أو خط إنتاج، ثم نحدد نسب المزج (**Mixing Ratios - `CK94`**) ليحسب النظام تكلفة معيارية مرجحة (Weighted Average Standard Price).

### 🔹 #90. What is Actual Costing or Material Ledger?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #90:** What is Actual Costing or Material Ledger?
> **Answer:** Actual Costing, often known as Material Ledger, is an SAP feature that calculates the actual periodic cost of a product. Inventory can be revalued (based on real cost computation) and related accounting entries can be generated as an option.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — ممتازة، مع إضافة تحديث S/4HANA`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يقوم **Material Ledger (ML)** بتجميع فروق الأسعار والانحرافات طوال الشهر، وفي نهاية الشهر يتم تشغيل **Actual Costing Run (`CKMLCP`)** لاحتساب السعر الفعلي الدوري (**Periodic Unit Price - PUP / Price Control `V` at month-end**). **ملاحظة S/4HANA:** تفعيل **Material Ledger** أصبح **إجبارياً (Mandatory)** في S/4HANA لتقييم المخزون بعملات متعددة، بينما يظل تشغيل Actual Costing (`CKMLCP`) اختيارياً.

### 🔹 #91. What is Costing Variant?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #91:** What is Costing Variant?
> **Answer:** The costing variant describes how a cost estimate determines the standard price.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — مختصرة جداً وتغفل المكونات الأساسية للـ Costing Variant`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في المقابلات، السؤال عن **Costing Variant (`OKKN` - مثل `PPC1`)** يتطلب ذكر مكوناته الرئيسية التي يتحكم بها:
> 1. **Costing Type:** يحدد الغرض من التكلفة وما إذا كانت ستُحدث حقل Standard Price.
> 2. **Valuation Variant:** يحدد استراتيجية تسعير الخامات والأنشطة والأعباء الإضافية (Costing Sheet).
> 3. **Date Control:** يتحكم في تواريخ صلاحية التكلفة وتاريخ تفجير الـ BOM والـ Routing.
> 4. **Quantity Structure Control:** يحدد كيفية اختيار الـ BOM والـ Routing.

### 🔹 #92. What is Cost Component Structure?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #92:** What is Cost Component Structure?
> **Answer:** Cost Component Structure is the method of depicting a product’s cost in a concise and meaningful manner, which is utilized for various decision-making objectives. The display of product cost estimates is determined by the Cost component views. Each cost component can be variable or fixed in nature.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة ممتازة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يُعرّف عبر **`OKTZ`** ويُقسم تكلفة المنتج إلى شرائح واضحة (مثل: Raw Materials، Packaging، Machine Cost، Direct Labor، Production Overhead) مع ربط كل شريحة بنطاق من **Cost Elements**.

### 🔹 #93. What is Standard Cost Estimate Release?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #93:** What is Standard Cost Estimate Release?
> **Answer:** Cost estimate release is the action of determining the production cost of manufactured material and releasing it as a standard price.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة، ويفضل توضيح الفرق بين Marking و Releasing`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يتم ذلك عبر **`CK24`** على مرحلتين:
> 1. **Marking (التأشير):** يفتح النظام السماح بالتأشير (`Allow Marking`) فيُحدث التكلفة المحسوبة في حقل **Future Standard Price** في Material Master (`Accounting 1`).
> 2. **Releasing (الاعتماد/الإطلاق):** ينقل القيمة من Future Price إلى **Current Standard Price**، وإذا كان هناك مخزون حالي يتولد قيد محاسبي تلقائي لإعادة تقييم المخزون (`UMBS`).

### 🔹 #94. What is the Prerequisite of Standard Cost Estimate?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #94:** What is the Prerequisite of Standard Cost Estimate?
> **Answer:** A costing variant can be used to generate a standard cost estimate. The costing variant includes the following settings for standard cost estimates:
> - The costing type specifies that the costing results can be updated as the standard price in the material master.
> - The valuation variation states that the materials are valued at the standard price; and
> - The BOM Application stipulates that costing must be released.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟡 3.5/5 — تركز فقط على إعدادات الـ Costing Variant وتغفل البيانات الرئيسية المطلوبة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** بالإضافة إلى إعدادات **Costing Variant** المذكورة، تشمل المتطلبات العملية (Master Data Prerequisites) قبل حساب التكلفة المعيارية:
> - تهيئة **Material Master (`MM01`)** مع تبويبات Accounting 1/2 و Costing 1/2 (وتحديد Price Control = `S`).
> - وجود **BOM (`CS01`)** صالحة وفعالة للتكاليف.
> - وجود **Routing (`CA01`)** و **Work Centers (`CR01`)** مربوطة بـ Cost Centers و Activity Types.
> - إدخال أسعار الأنشطة المخططة في **`KP26`** وأسعار المواد الخام.

### 🔹 #95. What is the Process of Standard Cost Estimate?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #95:** What is the Process of Standard Cost Estimate?
> **Answer:** The process of costing run is as follows:
> - Creation of Costing run
> - Selecting materials for costing run
> - Exploding BOM’s for costing run
> - Executing costing run
> - Analyzing the costing run
> - Marking of standard cost estimate
> - Releasing of standard cost estimate

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة ممتازة ومرتبة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** هذه هي خطوات **`CK40N` (Edit Costing Run)** القياسية. ملاحظة لمقابلات **S/4HANA:** تم تبسيط خطوات `CK40N` في S/4HANA بدمج Selection و Structure Explosion في خطوة واحدة لتسريع الأداء.

### 🔹 #96. How to Calculate the Joint Product or Co-Product Cost in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #96:** How to Calculate the Joint Product or Co-Product Cost in SAP?
> **Answer:** The cost of the joint product will be calculated using a standard cost estimate in the costing run (T-Code CK40N). Furthermore, an apportionment structure must be created in the material master of the two joint products, which will decide how the cost of production will be distributed between the two co-products at the time of standard cost estimate.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة ممتازة ودقيقة تقنياً`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** توضيح إضافي: يتم تفعيل خيار **Co-Product** في شاشة Material Master (`MRP 2` / `Costing 1`) وإدخال **Apportionment Structure** (هيكل التوزيع النسبى باستخدام Equivalence Numbers) لتوزيع تكلفة العملية الإنتاجية المشتركة بين المنتجات المشتركة (Co-Products).

### 🔹 #97. How to Calculate the Cost of By-Product?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #97:** How to Calculate the Cost of By-Product?
> **Answer:** The by-product is also listed as a negative component in the main product’s BOM (output). However, the cost of the by-product is unrelated to the cost of the main product. It is usually set at a standard price, which is either the expected cost of production or market value, whichever is lower.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة نموذجية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** إجابة ممتازة. لأن الـ **By-Product (المنتج الثانوي)** يدخل بكمية سالبة في الـ BOM الخاصة بالمنتج الرئيسي، فإن قيمته تُخصم تلقائياً من إجمالي تكلفة تصنيع المنتج الرئيسي (Net Realizable Value / Standard Price deduction).

### 🔹 #98. What are Normal Loss And Abnormal Loss in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #98:** What are Normal Loss And Abnormal Loss in SAP?
> **Answer:** In a manufacturing process, the normal loss is the difference between input and output materials. This is the average loss seen over a period of time, and it is already determined in the BOM.
> The loss that is unique to a given production batch is referred to as abnormal loss. It is in addition to normal loss and is not considered when computing the standard BOM.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 4.5/5 — دقيقة، مع ربطها بمصطلحات SAP Scrap`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** في SAP يُعرف الفاقد الطبيعي بـ **Planned Scrap** (ويُعرّف كنسبة مئوية في Material Master أو BOM أو Routing: Assembly Scrap، Component Scrap، Operation Scrap) ويدخل ضمن التكلفة المعيارية للمنتج. أما الفاقد غير الطبيعي (**Unplanned Scrap / Abnormal Loss**) فيظهر كـ **Scrap Variance** عند التسوية في نهاية الفترة ويُحمل على قائمة الدخل.

### 🔹 #99. What is Production Variance in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #99:** What is Production Variance in SAP?
> **Answer:** Production variance is the difference between net actual costs charged to the order and targeted costs based on the initial cost estimate and amount delivered to inventory.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة دقيقة`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** يتم احتساب الانحرافات عبر **`KKS2`** (لأمر واحد) أو **`KKS1`** (مجمعة) وتُرحل عند التسوية (`KO88` / `CO88`) إلى حساب فروق الإنتاج (`PRD`) و CO-PA. وتنقسم إلى انحرافات مدخلات (**Input Variances:** Input Price, Input Quantity, Resource-Usage) وانحرافات مخرجات (**Output Variances:** Lot Size, Mixed-Price, Output Price).

### 🔹 #100. What is the Price Difference in SAP?

> 📄 **[النص الأصلي من الملف — Original PDF Text]**
> **Question #100:** What is the Price Difference in SAP?
> **Answer:** Price differences occur for materials valued at the standard price in all movements and invoices with a value that differs from the standard price.

> [!TIP]
> 🎯 **تقييم الإجابة (Evaluation):** `🟢 5/5 — إجابة نموذجية`
>
> ✨ **التحسين والإضافة المهنية (Added Expert Review):** عند تقييم الصنف بالسعر المعياري (**Price Control `S`**)، يثبت المخزون دائماً بالسعر المعياري، وأي فرق بين سعر أمر الشراء/الفاتورة والسعر المعياري يُرحل تلقائياً إلى حساب فروق الأسعار (**Price Difference Account - Transaction Key `PRD` in `OBYC`**). أما إذا كان الصنف مقيماً بالمتوسط المتحرك (**Moving Average Price `V`**)، فإن الفرق يُعدّل قيمة المخزون مباشرة (`BSX`) بشرط توفر رصيد كافٍ من المخزون يغطي الكمية المفوترة.
