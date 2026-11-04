# Telco Customer Churn Analysis

Проект по анализу и прогнозированию оттока клиентов телеком-компании.

Сначала я посмотрел, какие группы клиентов чаще уходят, а затем построил две модели бинарной классификации:

- Logistic Regression
- Random Forest

Для оценки использовал ROC-AUC, Precision, Recall и F1.  
Порог классификации подбирал отдельно на validation-выборке, чтобы увеличить долю найденных клиентов с риском ухода.

В проекте также есть:

- обработка и подготовка данных;
- анализ оттока по сегментам;
- train / validation / test split;
- preprocessing через `Pipeline` и `ColumnTransformer`;
- матрица ошибок;
- коэффициенты Logistic Regression;
- feature importance Random Forest;
- интерпретация результата с точки зрения retention-задачи.

## Стек

Python, Pandas, Matplotlib, Seaborn, scikit-learn, Jupyter Notebook

## Файлы

- `telco-churn-analysis.ipynb` — основной анализ
- `WA_Fn-UseC_-Telco-Customer-Churn.csv` — датасет
