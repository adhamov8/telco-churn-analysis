# Telco Customer Churn Analysis

Проект по анализу и прогнозированию оттока клиентов телеком-компании.

Сначала я посмотрел, какие группы клиентов чаще уходят, а затем сравнил две модели бинарной классификации:

- Logistic Regression
- Random Forest

Для оценки использовал ROC-AUC, Precision, Recall и F1. Порог классификации подбирал отдельно на validation-выборке.

## Результаты

На validation ROC-AUC составил примерно **0,835** у Random Forest и **0,829** у Logistic Regression. На test модели показали практически одинаковый результат — около **0,85 ROC-AUC**.

Для Random Forest на validation был выбран порог около **0,276**. При таком пороге на test:

- найдено **258 из 280** реально ушедших клиентов;
- recall — около **92%**;
- precision — около **42%**;
- как риск оттока отмечены **613 из 1 057** клиентов.

То есть модель можно использовать для приоритизации retention-кампании, если важнее не пропустить потенциально уходящих клиентов. При этом высокая полнота достигается ценой большого числа ложных срабатываний, поэтому эффективность конкретного retention-предложения нужно проверять отдельно, например через A/B-тест.

## Что есть в проекте

- обработка и подготовка данных;
- анализ оттока по сегментам;
- train / validation / test split со stratify;
- preprocessing через `Pipeline` и `ColumnTransformer`;
- Logistic Regression и Random Forest;
- ROC-AUC, Precision, Recall и F1;
- подбор threshold на validation;
- матрица ошибок;
- коэффициенты Logistic Regression;
- feature importance Random Forest.

## Стек

Python, Pandas, Matplotlib, Seaborn, scikit-learn, Jupyter Notebook

## Файлы

- `telco-churn-analysis.ipynb` — основной анализ
- `WA_Fn-UseC_-Telco-Customer-Churn.csv` — датасет
