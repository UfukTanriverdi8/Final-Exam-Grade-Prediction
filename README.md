# Final Exam Grade Prediction

This project aims to predict the final exam grades of students using various features such as study time, previous grades, and other related attributes. By using linear regression, this project evaluates different feature selection to find the selection with the most accuracy.\
Here you can run the code from [Google Colab](https://colab.research.google.com/drive/1Gog5eESZP0aaeh5ZTrrQZopctg7GQf_-?usp=sharing).

## Dataset

The dataset used in this project is sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/320/student+performance). It includes various features about students' academic performance, socio-economic status, and study habits. We will just use the data with the math exam grades which is called `student-mat.csv`.

**Features**

1. `school`: Student's school (binary: `"GP"` - Gabriel Pereira or `"MS"` - Mousinho da Silveira)
2. `sex`: Student's sex (binary: `"F"` - female or `"M"` - male)
3. `age`: Student's age (numeric: from 15 to 22)
4. `address`: Student's home address type (binary: `"U"` - urban or `"R"` - rural)
5. `famsize`: Family size (binary: `"LE3"` - less or equal to 3 or `"GT3"` - greater than 3)
6. `Pstatus`: Parent's cohabitation status (binary: `"T"` - living together or `"A"` - apart)
7. `Medu`: Mother's education (numeric: `0` - none, `1` - primary education (4th grade), `2` – 5th to 9th grade, `3` – secondary education, or `4` – higher education)
8. `Fedu`: Father's education (numeric: `0` - none, `1` - primary education (4th grade), `2` – 5th to 9th grade, `3` – secondary education, or `4` – higher education)
9. `Mjob`: Mother's job (nominal: `"teacher"`, `"health"` care related, civil `"services"` (e.g. administrative or police), `"at_home"`, or `"other"`)
10. `Fjob`: Father's job (nominal: `"teacher"`, `"health"` care related, civil `"services"` (e.g. administrative or police), `"at_home"`, or `"other"`)
11. `reason`: Reason to choose this school (nominal: close to `"home"`, school `"reputation"`, `"course"` preference, or `"other"`)
12. `guardian`: Student's guardian (nominal: `"mother"`, `"father"`, or `"other"`)
13. `traveltime`: Home to school travel time (numeric: `1` - <15 min., `2` - 15 to 30 min., `3` - 30 min. to 1 hour, or `4` - >1 hour)
14. `studytime`: Weekly study time (numeric: `1` - <2 hours, `2` - 2 to 5 hours, `3` - 5 to 10 hours, or `4` - >10 hours)
15. `failures`: Number of past class failures (numeric: `n` if `1 <= n < 3`, else `4`)
16. `schoolsup`: Extra educational support (binary: `yes` or `no`)
17. `famsup`: Family educational support (binary: `yes` or `no`)
18. `paid`: Extra paid classes within the course subject (Math or Portuguese) (binary: `yes` or `no`)
19. `activities`: Extra-curricular activities (binary: `yes` or `no`)
20. `nursery`: Attended nursery school (binary: `yes` or `no`)
21. `higher`: Wants to take higher education (binary: `yes` or `no`)
22. `internet`: Internet access at home (binary: `yes` or `no`)
23. `romantic`: With a romantic relationship (binary: `yes` or `no`)
24. `famrel`: Quality of family relationships (numeric: `1` - very bad to `5` - excellent)
25. `freetime`: Free time after school (numeric: `1` - very low to `5` - very high)
26. `goout`: Going out with friends (numeric: `1` - very low to `5` - very high)
27. `Dalc`: Workday alcohol consumption (numeric: `1` - very low to `5` - very high)
28. `Walc`: Weekend alcohol consumption (numeric: `1` - very low to `5` - very high)
29. `health`: Current health status (numeric: `1` - very bad to `5` - very good)
30. `absences`: Number of school absences (numeric: `0` to `93`)
31. `G1` - first period grade (numeric: from 0 to 20)
31. `G2` - second period grade (numeric: from 0 to 20)
32. `G3` - final grade (numeric: from 0 to 20, output target)

## Files

- `student-mat.csv`: The file that contains the math grades. This is what we're going to use.
- `student-por.csv`: The file that contains the Portuguese grades.
- `final_grade_prediction.ipynb`: Jupyter Notebook containing the code for data loading, preprocessing, model training, evaluation, and comparison.
- `README.md`: This file, providing an overview of the project.

## Results
- The project evaluates each model's performance using Mean Absolute Error (MAE), Mean Squared Error (MSE), and R2 score metrics. Most of the evaluation is made by looking at mean cross valdiaton R2 scores.
- The final grade mostly just depends on the past two exams. No features other than these two exams correlates with the final grade enough to be used in the training and get a reasonable accuracy.
- If we try to increase the accuracy by adding other features than past two exam scores, we just make the accuracy worse. So the model literally does not accept any feature other than first two exam scores(G1 and G2).
- This dataset is a great introduction to linear regression. We have one target variable and we can use two features to get a pretty good accuracy. This means that we can easily visualize the data points and our prediction surface to see what is going on.
