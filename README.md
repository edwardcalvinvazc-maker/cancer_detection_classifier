# 🎗️ Cancer Detection: An Ensemble Journey

Welcome to my journey into building a cancer detection classifier! This repository tells the story of how I tackled the challenging task of classifying cancer data using machine learning, specifically focusing on an ensemble approach.

## 📖 The Story Begins: What is this about?

It started with a crucial real-world problem: accurately predicting cancer based on medical data. When dealing with medical diagnoses, the cost of missing a positive case (a false negative) can be life-threatening. My goal was to create a robust model that minimizes these missed detections while maintaining high overall accuracy.

To achieve this, I decided to use the **Ensemble Method**, specifically a technique called **Stacking**. Think of it as assembling a team of expert doctors, where each doctor gives their diagnosis, and a head doctor makes the final call based on their opinions.

## 🛠️ The Journey: What I Did

I started with a dataset (`cancer_dataset.csv`) filled with various features like radius, texture, perimeter, and area of cell nuclei.

To build my "team of experts", I selected two powerful base models (the initial doctors):
1.  **RandomForestClassifier (b1)**: Known for its robustness and ability to handle complex, non-linear data by building multiple decision trees.
2.  **HistGradientBoostingClassifier (b2)**: A fast and efficient model that builds trees sequentially, learning from the mistakes of the previous ones.

These models independently analyze the data and make their predictions. But I didn't stop there. I needed the "head doctor" to combine their knowledge.

For the final decision-maker (the meta-classifier), I used:
*   **LogisticRegression**: A simple yet effective model that takes the outputs from the Random Forest and Gradient Boosting models and learns how best to combine them for the final diagnosis.

I then fine-tuned the model's decision threshold. In medical scenarios, we often want to be extra cautious. By adjusting the threshold, I aimed to drastically reduce the number of False Negatives (actual positive cases that are missed).

## 🎉 The Destination: What's the Result?

The results of this ensemble approach were fantastic!

After adjusting our model to be cost-sensitive (prioritizing the reduction of missed cancer cases), here is what we achieved:
*   **Zero Missed Cases (0 False Negatives)**: At our chosen threshold, the model did not predict *any* actual positive cases as negative. This means 0 cancer cases were missed in our test set!
*   **High Accuracy**: Despite the cautious threshold, the model still maintained an impressive overall accuracy of **93.7%**.

You can see the visual proof of this in the included `Confussion Matrix.png`, which shows the perfect score of 0 in the False Negative quadrant.

The full code and step-by-step process can be found in the `cancer_ensemble.ipynb` notebook. Feel free to explore how this team of models came together to save the day!
