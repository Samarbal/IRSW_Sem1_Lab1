# Lab 01 Worksheet — ورقة عمل المختبر

الاسم / Name: Samar Mohammed Balousha     الرقم الجامعي / Student ID: 2320222601

## A. Read the representation — قراءة التمثيل

1. اختر المورد R09. ما قيم الأعمدة المناظرة له في صفوف `topic_python`, `lang_ar`, `access_free`, `type_notebook`؟ Explain each value.

**Answer**:

For resource R09, all four incidence values are 1: 
- `topic_python`: 1 (The resource is tagged with the Python topic.)
- `lang_ar`: 1 (The resource is in Arabic.)
- `access_free`: 1 (The resource is freely accessible.)
- `type_notebook`: 1 (The resource is a notebook.)

---

2. لماذا لا تتغير قيمة الوجود إذا تكررت كلمة عشر مرات؟ Why does repetition not increase a binary incidence value?

**Answer**: 

 We use set(tokenize(...)) to remove duplicate terms. The binary incidence matrix records only presence (1) or absence (0), not term frequency.


--- 

3. ما المجموعة التي نطبق عليها NOT؟ What is the universe for NOT in this lab?

**Answer**: The universe for NOT is the current collection of 12 resources (R01–R12). NOT complements a Boolean vector within this collection only, not across all possible documents.

---  

## B. Predict and verify — توقع ثم تحقق

For each query, predict IDs before running the notebook. Keep the original predictions visible.

| Task | Predicted IDs / التوقع | Actual IDs / النتيجة | Explanation / التفسير |
|---|---|---|---|
| Q1 | R01, R09 |R01, R09 | Python topic, beginner level, Arabic language, and free access.   |
| Q2 | r4 , r5  | r4 , r5   | IR topic, use Arabic or English, are free, and are not advanced.  |
| Q3 | R03 , R06    , R09  , R11 | R03 , R06    , R09  , R11 | Python or NLP, are notebooks, and are free |
| Q4 |R08 | R08|web development, is free, and is not marked as paid|


---- 


Explain Q2 or Q3 column by column for two resources: one included and one excluded.
فسر الاستعلام Q2 أو Q3 لموردين: أحدهما ظهر والآخر لم يظهر.

**Answer**:

**Q2 — Included and Excluded Resources**

**Included: R04**
- `topic_ir = 1`
- `(lang_ar OR lang_en) = 1`
- `access_free = 1`
- `NOT level_advanced = 1`

R04 satisfies all conditions, so it is included.

**Excluded: R09**
- `topic_ir = 0`
- `(lang_ar OR lang_en) = 1`
- `access_free = 1`
- `NOT level_advanced = 1`

R09 is excluded because it is tagged with Python, not Information Retrieval.

---


## C. Matching and usefulness — المطابقة والفائدة

1. متعلم مبتدئ يريد كتابة شيفرة خلال ساعة، ويقرأ العربية فقط. قارن R01 وR09 واختر الأنسب مع سببين. Which metadata or description supports your choice?

**Answer**: 
R01 is an Arabic video tutorial, while R09 is an Arabic notebook.

I would choose R09 because:

- It is a notebook that allows hands-on coding practice.

- It includes practical exercises and takes 60 minutes, matching the learner's goal.


2. يظهر R12 عند البحث بكلمة بايثون. هل هذا مورد مناسب لتعلم بايثون عمليا؟ Explain why a word match can be correct while its result is unhelpful for this need.

**Answer**: No. R12 mentions Python, but it is not a practical Python tutorial. A word match does not always mean the resource is relevant to the learner's needs.

--- 


3. قارن نتائج `python`, `بايثون`, اتحادهما و`topic_python`. What is missed or added, and why?

**Answer**:

Based on the experiment results:

- **English word:** R02, R10
- **Arabic word:** R01, R03, R09, R11, R12
- **Either word:** R01, R02, R03, R09, R10, R11, R12
- **Topic tag:** R01, R02, R03, R09, R10, R11

A single-language query misses resources using the other language. The union retrieves both groups but also includes R12, which mentions Python without being a practical learning resource. The curated topic tag excludes R12.

---
4. هل `topic_python` يثبت أن النظام يترجم أو يفهم المعنى آليا؟ Explain how the supplied catalog tags bridge the two languages.

**Answer**: No, the tag is manually provided in the catalog to connect Arabic and English resources under the same topic. The system does not automatically translate or understand their meaning.


----
5. لا يعيد Boolean retrieval ترتيبا بدرجة الصلة. اقترح معلومتين قد تساعدان على ترتيب الموارد لحاجة معينة، دون تنفيذ نموذج ترتيب. Suggest two possible ranking signals.

**Answer**:
- Resource level: How well the difficulty matches the learner's experience.

- Resource format: Whether the resource is a video, notebook, or article, depending on the learner's goal
--- 

## D. One new search need — حاجة جديدة

اكتب حاجة واقعية من دراستك وصغ لها استعلاما باستخدام الوسوم المتاحة. ثم توقع النتيجة وشغلها.
Write your need, Boolean expression, predicted IDs, actual IDs and one limitation.

- Need / الحاجة: i need free english resources to learn more about information retrieval. 
- Expression / الاستعلام: topic_ir AND lang_en AND access_free
- Predicted / التوقع: R04
- Actual / النتيجة: R04 and R06
- Limitation / القيد: Boolean retrieval checks whether the conditions match, but it does not evaluate the quality of the resource.

## Submission — التسليم

- Completed notebook with your functions and outputs / الدفتر مع الشيفرة والمخرجات.
- This worksheet with your own explanations / هذه الورقة بإجاباتك وتفسيرك.
- Optional: record any added fictional resource and its effect / سجل أثر المورد الإضافي إن أضفته.

https://github.com/telsayed/IR-in-Arabic/tree/master/Summer2021 

Follow the course announcement for the deadline and assessment rules.
موعد التسليم وآلية التقييم حسب الإعلان الرسمي للمساق.
