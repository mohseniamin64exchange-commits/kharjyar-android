# معیار پذیرش فاز دوم

## Entityهای مورد انتظار

- TransactionEntity
- PendingTransactionEntity
- AccountEntity
- CategoryEntity
- BudgetEntity
- MerchantRuleEntity
- MessagePatternEntity
- RecurringTransactionEntity
- DebtEntity
- DebtPaymentEntity
- TagEntity
- TransactionTagCrossRef

## Enumهای مورد انتظار

- TransactionType
- TransactionDirection
- TransactionStatus
- TransactionSource
- AccountType
- CurrencyDisplayMode
- RecurrenceType
- DebtType
- DebtStatus

## Indexهای کلیدی مورد انتظار

- transactionDateTime
- accountId
- categoryId
- fingerprint
- status
- transactionType
- direction
- linkedTransferId

## دسته‌های پیش‌فرض (۲۷ مورد)

1. خوراک و رستوران
2. مواد غذایی
3. خرید منزل
4. پوشاک
5. رفت‌وآمد
6. تاکسی و کرایه
7. سوخت
8. تعمیر خودرو
9. قبوض
10. اینترنت و تلفن
11. اجاره و مسکن
12. درمان و دارو
13. آموزش
14. تفریح
15. سفر
16. هدیه
17. کمک و خیریه
18. قسط
19. بدهی
20. خدمات
21. خرید اینترنتی
22. پس‌انداز
23. سرمایه‌گذاری
24. انتقال بین حساب‌ها
25. حقوق
26. درآمد
27. سایر

درج باید idempotent باشد. نوع دسته درآمدی، هزینه‌ای یا انتقالی باید مانع اختصاص ناسازگار شود.

## تست‌های مورد انتظار

- درج/دریافت حساب و دسته
- درج، ویرایش و حذف امن تراکنش
- Foreign Keyها
- جلوگیری از Fingerprint تکراری
- انتقال داخلی و اثر آن بر مانده
- خارج‌شدن انتقال داخلی از جمع درآمد و هزینه
- جمع درآمد و هزینه فقط برای تراکنش تأییدشده
- TypeConverterها
- عدم درج مجدد دسته‌های پیش‌فرض
- مبلغ‌های بزرگ با Long
- حذف حساب/دسته دارای تراکنش
- Room Database و Migration اولیه

## شرط تأیید

Build و تست واقعی باید موفق باشد. تست اجرا‌نشده نباید موفق اعلام شود و علت و روش اجرای آن باید گزارش شود.

