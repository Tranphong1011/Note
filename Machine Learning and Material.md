Additive manufacturing (AM) or additive layer manufacturing (ALM) is the industrial production name for [3D printing](https://www.twi-global.com/technical-knowledge/faqs/what-is-3d-printing "What is 3D Printing and How Does it Work?"), a computer controlled process that creates three dimensional objects by depositing materials, usually in layers.

Three types of materials can be used in additive manufacturing: **polymers, ceramics and metals**.
the goal of ML is the development of accurate predictive models
1. Ứng dụng ML vào AM (addtive manufactoring): Once an ML model is trained, AM users can interrogate the model with various questions, such as “what process parameter set should be used if we require ultimate tensile strength of Y?” or “what is the tradeoff between the different process parameter inputs?” or “which process parameter inputs have a large influence on part density?” This allows the AM user to rapidly develop optimized process parameters. Additionally, by monitoring the AM manufacturing process through testing coupon samples at regular intervals, the model can be further trained to detect process drift as a function of time or other factors (e.g., room temperature, humidity, personnel).
2. applying ML to real-time sensory inputs or measurements, such as using computer vision to monitor in-situ sensors

Machine Learning is about machines improving from data, knowledge, experience, and interaction.” -> we are going to address the concept of improving a machine’s performance from data, knowledge, experience and interaction
The key is being able to turn the massive amount of data generated into useful information to improve the machine’s performance.

Next to the data sets involved, the ability to leverage experience to automatically improve algorithms is key to appreciating Machine Learning

The learning types’ data inputs could be in the form of images, chemistries, sensor data, mechanical property data and volumetric information


3D printing process parameters are the settings that control the printing process of a 3D printer, which include various factors such as temperature, speed, layer height, and infill density. These parameters are essential to ensure that the final 3D printed product is of high quality and accuracy.

Temperature is a critical factor that affects the viscosity and flow characteristics of the filament material, which in turn affects the quality of the final product. The temperature of the printer's hot end needs to be set to the appropriate value for the specific type of filament used.

Printing speed is another factor that influences the quality of the final product. The speed of the extruder needs to be set in such a way that it does not compromise the accuracy of the print.

Layer height refers to the thickness of each printed layer, which can affect the overall quality and resolution of the print. A smaller layer height can produce a more detailed and higher resolution print, but it can also increase the printing time and may require a higher level of precision from the printer.

Infill density determines how much material is used to fill in the empty space inside the 3D printed object. Higher infill densities result in a stronger, more durable object, but they also require more material and time to print.

Other parameters that can be adjusted include the printing temperature of the bed, the printing speed of the cooling fan, and the retraction settings. These parameters can be fine-tuned based on the specific requirements of the 3D printing project.

Overall, understanding and optimizing the 3D printing process parameters is crucial for achieving high-quality, accurate 3D prints and maximizing the efficiency of the 3D printing process.


Topic:
1.  Optimizing Additive Manufacturing Process Parameters using Machine Learning: Investigate how machine learning algorithms can be used to optimize the 3D printing process parameters like layer thickness, build orientation, and infill patterns to achieve desired mechanical properties, surface finish, and material efficiency.
    
2.  Defect Detection and Quality Prediction in Additive Manufacturing using Supervised Learning: Develop a machine learning model that can automatically identify defects (such as incomplete fusions or voids) during the printing process and predict final product quality using sensor data, process parameters, and real-time monitoring of the printing progress.
    
3.  Materials Selection and Customization for Additive Manufacturing using Deep Learning: Explore how advanced predictive models can guide the selection of optimal materials for a given application or develop new material compositions with specific characteristics in the context of additive manufacturing processes.
    
4.  Generative Modeling for Topology Optimization in Additive Manufacturing: Implement generative design and machine learning algorithms to optimize 3D printed part geometry for improved strength-to-weight ratios, reduced material usage, and enhanced performance characteristics.
    
5.  Intelligent Support Structures for Additive Manufacturing using Reinforcement Learning: Create a reinforcement learning model capable of designing support structures that minimize material waste and post-processing efforts while maximizing printability and finished part quality.
    
6.  Predictive Maintenance and Process Monitoring for Additive Manufacturing Equipment: Develop machine learning models that can monitor machine health and anticipate maintenance needs to maximize machine uptime and ensure optimal performance in additive manufacturing facilities.


Title: Defect Detection and Quality Prediction in Additive Manufacturing using Supervised Learning

Abstract:

Additive Manufacturing (AM), also known as 3D printing, is a rapidly evolving technology with the potential to revolutionize the manufacturing industry. However, a major challenge in the widespread adoption of AM is the difficulty in ensuring product quality and detecting defects during the production process. This Master's research proposal aims to develop a novel method for defect detection and quality prediction in AM using supervised learning techniques. By training machine learning algorithms on high-quality datasets, we intend to develop a predictive model that can accurately identify defects and predict quality in real-time, enabling more efficient quality control and reducing the time and effort spent on post-production inspection.

1.  Introduction

Additive Manufacturing (AM) is a promising technology that allows for the production of complex geometries and customizable designs with minimal waste. However, one of the main challenges faced by practitioners is the assurance of product quality and the detection of defects during the manufacturing process. In traditional manufacturing, quality control often relies on post-production inspection and destructive testing, which can be time-consuming and costly. In AM, the challenge is even more significant as the process is characterized by the rapid deposition of layers and the formation of complex parts with intricate geometrical features.

Improving defect detection and quality prediction is crucial to the broader adoption of AM and has been the subject of numerous research works. Machine learning, particularly supervised learning techniques, have shown great potential in addressing this challenge. By utilizing a dataset containing samples of both defective and non-defective parts, supervised learning algorithms can be trained to detect defects and predict quality with high accuracy.

2.  Literature Review

Numerous studies have investigated the applicability of machine learning techniques for defect detection and quality prediction in AM. For instance, Wong et al. (2018) employed a Random Forest classifier to predict part quality in fused deposition modeling (FDM) by considering machine parameters, material properties, and other relevant factors. Similarly, Scime et al. (2020) used a Convolutional Neural Network (CNN) to analyze in-situ monitoring data and detect defects in laser powder bed fusion (LPBF).

Despite these advances, several gaps remain in the literature. First, most studies have focused on specific AM technologies or materials, with limited applicability to other contexts. Second, the quality of available datasets is often low, leading to less accurate models. This research aims to address these gaps by consolidating existing data sources and developing a unified supervised learning model for defect detection and quality prediction in AM, applicable to various technologies and materials.

3.  Methodology

3.1 Data Collection

A critical aspect of the research is the collection and preprocessing of high-quality datasets containing information about various AM processes, materials, defects, and quality parameters. Data will be sourced from various databases, including:

-   Proprietary datasets from industrial partners
-   Publicly available datasets from research institutions
-   AM process simulation datasets

Data preprocessing will involve cleaning, feature selection, and normalization to ensure consistency and improve the performance of the supervised learning model.

3.2 Model Development

Several supervised learning techniques, such as Support Vector Machines (SVM), Random Forests (RF), and Artificial Neural Networks (ANN), will be evaluated based on their performance in predicting defects and product quality. A combination of hyperparameter optimization and model validation techniques will be applied to ensure the selected model's generalizability and robustness.

3.3 Model Evaluation

The developed model will be evaluated using standard performance metrics, including accuracy, precision, recall, and F1-score. Additionally, the model's feedback will be used to improve the AM process and monitor potential defects in real-time.

4.  Expected Outcomes

The primary outcome of this research is the development of a novel supervised learning model capable of accurately detecting defects and predicting part quality in AM across various process technologies and materials. The model is expected to contribute to more efficient quality control in AM, enabling the production of high-quality parts with reduced time and effort spent on post-production inspection.

5.  Conclusion

The proposed Master's research project focuses on utilizing supervised learning techniques for the development of a robust model for defect detection and quality prediction in Additive Manufacturing. With the increasing adoption of AM technologies, such a model will contribute to the assurance of product quality and facilitate the broader integration of AM in various industries. By training the model on high-quality datasets and evaluating its performance using standard metrics, this research will contribute to the growing body of knowledge on AM quality control and machine learning applications.




Title: complicated supervised learning model

Introduction

Additive Manufacturing (AM), also known as 3D printing, has emerged as a revolutionary industrial technology in recent years. It offers a myriad of benefits, such as reduced production costs, rapid prototyping, increased geometric complexity of parts, reduced post-processing, and environment-friendly manufacturing processes. As the demand for high-quality and reliable printed parts grows, the need for an effective quality assurance and defect detection system becomes imperative. Machine learning, particularly supervised learning, offers great promise in addressing these challenges. This paper aims to discuss defect detection and quality prediction in additive manufacturing using supervised learning.

Section I: Additive Manufacturing: An Overview

1.1 Definition and Principles of Additive Manufacturing

Additive Manufacturing is a process of producing three-dimensional (3D) objects through the successive addition of layers of material. Unlike conventional manufacturing methods such as subtractive manufacturing or forming, AM has the advantage of minimal material waste and the ability to produce intricate geometries.

1.2 Types of Additive Manufacturing Technologies

Several AM technologies exist today, including Fused Filament Fabrication (FFF), Stereolithography (SLA), Selective Laser Sintering (SLS), and Electron Beam Melting (EBM). Each method has its unique strengths and application areas, but they all share common challenges in terms of quality control and defect detection.

Section II: Challenges in Additive Manufacturing

2.1 Types of Defects in Additive Manufacturing

The various types of defects that can occur in AM processes include, but are not limited to, voids, delamination, warping, shrinkage, and surface deformation. These defects can compromise the structural integrity, functionality, and aesthetic appeal of the finished product.

2.2 Quality Control and Defect Detection Challenges

Maintaining quality control and detecting defects in AM processes can be difficult due to the unique challenges associated with the manufacturing process, such as varying material characteristics, size and shape limitations, and the layer-by-layer approach. Traditionally, quality assurance in manufacturing has relied upon post-processing inspection and destructive testing, which can lead to significant material waste and increased production time.

Section III: Supervised Learning for Defect Detection and Quality Prediction

3.1 Introduction to Supervised Learning

Supervised learning is a subset of machine learning that involves training a model based on labeled data. The goal is to use this information to make predictions or decisions for new, unseen data with similar characteristics to the training set. This type of machine learning is especially suitable for defect detection and quality prediction in additive manufacturing due to the availability of historical data and the known relationship between input parameters and the desired output.

3.2 Applications of Supervised Learning in Additive Manufacturing

Supervised learning techniques can be employed for various purposes in additive manufacturing, such as predicting print quality, detecting defects, and optimizing process parameters. Some common supervised learning algorithms include linear regression, logistic regression, decision trees, and artificial neural networks.

3.3 Process Monitoring and Sensor Data

By incorporating data from various sensors present in AM machines, such as temperature, pressure, and optical sensors, it is possible to monitor the process in real-time and detect defects during the manufacturing process. This real-time feedback can either be used to adjust process parameters or halt the printing for corrections, ultimately leading to improved outcomes.

3.4 Case Studies and Examples

Several recent studies demonstrate the application of supervised learning techniques in additive manufacturing:

-   A study by Yang et al. (2019) used supervised learning (Support Vector Machines) for defect detection in Selective Laser Melting (SLM), achieving a 90% accuracy in classifying defects.
-   Zimina et al. (2021) developed a machine learning model to predict the quality of printed parts based on process parameters, reporting a prediction accuracy of over 85%.
-   In another study, Cartiaux et al. (2020) employed decision trees to optimize print parameters and minimize the occurrence of voids in Fused Filament Fabrication (FFF).

Conclusion

In conclusion, supervised learning offers a promising solution to the challenges faced by additive manufacturing in terms of quality control and defect detection. By using historical data and real-time sensor information, machine learning models can predict part quality, detect defects, and optimize the AM process. As the technology and algorithms continue to evolve, it is expected that the accuracy and capabilities of these models will only improve, further revolutionizing additive manufacturing and its applications in various industries.


Title: Defect Detection and Quality Prediction in Additive Manufacturing using Supervised Learning

1.  Introduction to Additive Manufacturing

Additive Manufacturing (AM), also known as 3D printing, is a transformative process that allows for the creation of complex, customizable, and intricate parts by adding successive layers of material. This technology has revolutionized manufacturing across multiple industries, including aerospace, automotive, medical, and consumer goods. One of the main advantages of AM is the ability to create parts with complex geometries that were previously not possible with traditional manufacturing methods. Despite its numerous benefits, AM remains challenged by the occurrence of defects and variations in quality, which can compromise the structural integrity and performance of the printed parts.

(Include an image of an example of 3D printing technology, such as a 3D printer or a printed part)

2.  The Importance of Defect Detection and Quality Prediction in AM

Detecting defects and improving quality control are critical aspects of AM, as they ensure the reliability and functionality of the printed parts. Some common defects that occur in AM include porosity, surface roughness, and geometric inaccuracies, all of which can negatively impact mechanical properties and performance. Early detection of these defects allows for timely intervention, resulting in reduced production time and costs, improved part quality, and increased confidence in the technology's adoption.

(Include an image illustrating common defects in 3D printed parts)

3.  Supervised Learning in Defect Detection and Quality Prediction

Supervised Learning is a branch of Machine Learning that uses labeled datasets to train algorithms to make predictions or classifications based on input data. In the context of AM, Supervised Learning can be applied to analyze data from sensors and imaging systems during the printing process to detect defects and predict the quality of the printed parts. Common Supervised Learning algorithms used in this context include:

-   Support Vector Machines (SVM)
-   Decision Trees
-   Random Forests
-   Neural Networks
-   k-Nearest Neighbors

(Include an image or schematic representing the Supervised Learning process)

4.  Data Acquisition and Preprocessing in Defect Detection and Quality Prediction

The first step in applying Supervised Learning to detect defects and predict quality in AM is acquiring data during the printing process. This data can be collected using a variety of sensors, including optical, thermal, and acoustic sensors, as well as imaging systems such as X-ray computed tomography or high-resolution cameras. After data acquisition, preprocessing is essential for removing noise or irrelevant features, standardizing the data, and integrating multiple data sources.

(Include an image illustrating data acquisition and preprocessing steps)

5.  Feature Extraction and Selection in Defect Detection and Quality Prediction

Feature Extraction involves transforming the raw data collected during the printing process into a set of features or attributes that can be efficiently analyzed by Supervised Learning algorithms. This step typically involves techniques such as Principal Component Analysis (PCA), Wavelet Transform, or Fourier Transform. Once features are extracted, Feature Selection methods, like Recursive Feature Elimination or Boruta, can be used to identify the most relevant features for detecting defects and predicting quality in AM.

(Include an image representing Feature Extraction and Selection process)

6.  Model Training, Validation, and Testing

After preprocessing and feature extraction, the data is split into training, validation, and testing sets. The training set is used to train the chosen Supervised Learning algorithm, while the validation set is employed to fine-tune the model's parameters. The testing set is reserved for evaluating the model's performance at detecting defects and predicting quality. This step is essential for understanding the model's generalization capabilities and mitigating the risk of overfitting.

(Include an image or diagram depicting the training, validation, and testing process)

7.  Implementing Supervised Learning in Real-World AM Applications

Implementing Supervised Learning models for defect detection and quality prediction requires close collaboration between AM practitioners and data scientists. Real-time monitoring and data analysis can offer invaluable feedback for process adjustments, ultimately leading to improved part quality and reduced costs in AM production. Successful application of Supervised Learning in AM can advance the technology's adoption and expand its use across various industries.

(Showcase some examples or case studies of Supervised Learning successfully applied in Additive Manufacturing)

Conclusion

Defect detection and quality prediction are essential factors for the successful application of Additive Manufacturing in various industries. Supervised Learning offers a promising approach to enhance quality control and detect defects in real-time, ultimately leading to improved part reliability and expanded use of AM technology. Collaborative efforts between data scientists and AM practitioners can pave the way for innovations in producing complex structures and custom parts, transforming manufacturing across multiple sectors.

-----------
Kĩ thuật bootstraping: Giả sử tính mean
  
```
When you simply calculate the average score from the original dataset, you are assuming that the distribution of the test scores is normal. However, this assumption may not be true in all cases. For example, the distribution of test scores may be skewed, or it may have outliers that can significantly affect the mean.

On the other hand, bootstrapping generates multiple bootstrap samples by resampling the original dataset with replacement (tức là 1 dataset có 100 records. Thay vì mean cả record, thì chọn ngẫu nhiên 50 records có trùng nhau, hay còn gọi là "replacement", tính toán trung bình và đưa vào 1 danh sách, sau đó trung bình danh sách đó). This means that each bootstrap sample is a random subset of the original dataset, and may have different statistical properties than the original dataset. By generating multiple bootstrap samples and calculating the mean of each sample, you can get a more accurate estimate of the mean score and the variability of the score.
```
```python
import numpy as np

# Generate 100 random test scores
scores = np.random.randint(0, 100, 100)

# Method 1: calculate mean of the original dataset
mean1 = np.mean(scores)
print("Method 1: Mean of original dataset =", mean1)

# Method 2: bootstrap resampling to generate multiple means
n_samples = 1000
sample_size = 50
bootstrap_means = []
for i in range(n_samples):
    sample = np.random.choice(scores, sample_size, replace=True)
    bootstrap_means.append(np.mean(sample))
mean2 = np.mean(bootstrap_means)
print("Method 2: Mean of bootstrap means =", mean2)

```

Sự khác nhau giữa regression tasks và classification tasks:
```
In machine learning, there are two main types of tasks: classification and regression.

Classification is a type of supervised learning task where the goal is to predict which category a new observation belongs to based on a set of input features. In classification, the output variable is discrete or categorical, meaning that it takes on a finite number of values. For example, in the famous iris dataset, the task is to classify flowers into one of three categories based on their sepal length, sepal width, petal length, and petal width.

On the other hand, regression is also a type of supervised learning task where the goal is to predict a continuous numerical output based on a set of input features. In regression, the output variable is continuous, meaning that it can take on any value within a certain range. For example, in the Boston Housing dataset, the task is to predict the median value of owner-occupied homes in different Boston suburbs based on a set of input features such as crime rate, average number of rooms, and distance to employment centers.

In summary, classification predicts categorical output, while regression predicts numerical output.
```

Cây quyết định
    Weather
      /  \
  Sunny Rainy
    /     \
  Humid   Windy
   / \     / \
 Yes  No  Yes  No
If the weather is sunny, you would follow the left branch and check the humidity. If the humidity is high, the decision would be to play tennis, but if it's low, the decision would be not to play tennis. If the weather is rainy, you would follow the right branch and check the windiness. If the windiness is high, the decision would be not to play tennis, but if it's low, the decision would be to play tennis.


Random Forest Calssifier:
![[Pasted image 20230508170845.png]]
```python
from sklearn import datasets
from sklearn.svm import SVC
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Load the iris dataset
iris = datasets.load_iris()
X = iris.data
y = iris.target

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a SVM classifier with linear kernel
clf = SVC(kernel='linear', random_state=42)

# Train the classifier on the training set
clf.fit(X_train, y_train)

# Use the trained classifier to predict the labels of the test set
y_pred = clf.predict(X_test)

# Evaluate the accuracy of the classifier
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)

```

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
# Load the Iris dataset
iris = load_iris()
X = iris.data[:, [0, 2]]  # select the first and third feature for visualization
y = iris.target
# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
# Create a Random Forest classifier with 100 trees
rf = RandomForestClassifier(n_estimators=100, random_state=42)
# Fit the model on the training data
rf.fit(X_train, y_train)
# Make predictions on the testing data
y_pred = rf.predict(X_test)
# Calculate the accuracy of the model
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)
# Plot the decision boundary

x_min, x_max = X[:, 0].min() - 0.5, X[:, 0].max() + 0.5
y_min, y_max = X[:, 1].min() - 0.5, X[:, 1].max() + 0.5
xx, yy = np.meshgrid(np.arange(x_min, x_max, 0.1), np.arange(y_min, y_max, 0.1))
Z = rf.predict(np.c_[xx.ravel(), yy.ravel()])
Z = Z.reshape(xx.shape)
plt.figure()
plt.contourf(xx, yy, Z, alpha=0.4)
plt.scatter(X[:, 0], X[:, 1], c=y, alpha=0.8)
plt.xlabel('Sepal length')
plt.ylabel('Petal length')
plt.show()
```
![[Pasted image 20230508173059.png]]
Sự khác nhau giữa mean và mode:
```
Mean is the sum of all values in a data set divided by the total number of values. It is a measure of the average value of a set of data. Mean is sensitive to extreme values, also known as outliers, in the data set.

Mode is the value that appears most frequently in a data set. It is a measure of the most common value in a set of data.![[Pasted image 20230508173030.png]] Mode is useful when analyzing data that has a lot of repetition or a few distinct peaks.
```
```
            age <= 40
            /      \
   income <= 50k   income > 50k
      /      \        /      \
   Class1  Class2   Class3   Class4

```

![[Pasted image 20230508175512.png]]
0399877910
Phong -ttphong1011@gmail.com
Hoàng K14 - - theguardian1011@gmail.com
Xuân - xuanphamake@gmail.com
Huy - anhhuydeptrai@gmail.com
Khoa - phamkhoamerce@gmail.com
Hiếu - anhphong4872@gmail.com
Bảo - matbaogalaxy323@gmail.com
Đỗ Linh - harmonyofcontrast97@gmail.com
Yên - yenlavie21@gmail.com
Hoa
Liên
Lộc
Lợi
Oanh
Hà 
Hường
Nhoc hà 
![[Pasted image 20230509154915.png]]

https://link.springer.com/article/10.1007/s00170-022-08995-7
A Convolutional Neural Network (CNN) classification to identify the presence of pores in powder bed fusion images
https://www.sciencedirect.com/science/article/pii/S2214860417302051?ref=pdf_download&fr=RR-2&rr=7c48f0912f4125e9
Application of supervised machine learning for defect detection during metallic powder bed fusion additive manufacturing using high resolution imaging.

https://pubs.aip.org/aip/acp/article/2393/1/020208/2822222/Application-of-machine-learning-in-fused
Application of machine learning in fused deposition modeling: A review