
### New Dataset Incoming:

* New curated image dataset specifically designed for Federated Learning
* Consists of 23326 images and categorized into 31 classes
### New Algorithms into the picture:

*  **Fed Cyclic :** Implements a cyclic mechanism for weight transmission and localized fine-tuning among users
* **Fed Star :** Fed Star algorithm provides advantages for Federated Learning 

* By applying federated learning to image classification , it enhances model training efficiency across distributed devices while improving security and privacy.

### Revision of Fed-Avg using Mathematics:
* In federated learning (FL), multiple clients (say K clients) work together to train a global model without sharing their individual data. Each client has its own data, and the goal is to find the best weights for the model, denoted as $w$, that minimize the overall loss across all clients' data.

1. Loss Function:
	* The loss function  $( L(x_i, y_i; w))$  measures how well the model with weights $w$ predicts the output $y_i$ for a given input $x_i$ .We want to minimize this loss.
2. Global Data : 
	* The Total Data $D$ is the sum of all individual clients' data:
				$D=\bigcup_{k=1}^{K}D_k$
		Where $D_k$ is the data of the $k$-th client
3. Minimization Goal : 
	* The overall goal is to minimize the average loss over all data:
			$\min \frac{1}{|D|}\sum_{i=1}^{|D|} L(x_i, y_i; w)$
4. Weighted Loss: 
	* We can rewrite the goal to account for each client's contribution:
			$\min \frac{1}{|D|} \sum_{k=1}^{K} \sum_{i=1}^{|D_k|} L(x_i, y_i; w)$
	* Here $L_k$ represents the average loss for the $k$-th client:
		* $L_k = \min \frac{1}{|D_k|} \sum_{i=1}^{|D_k|} L(x_i, y_i; w)$

### Simplifying the challenges and solutions in Federated Learning

##### Challenges with Fed-Avg:

**1. Communication Rounds :** Fed-Avg requires many rounds of communication between the central server and the clients before the global model converges to a good solution, especially when the data held by different clients is very different from each other.

**2. Accuracy Issues :**   The accuracy of the global model can decline because it is an average of all the local models. This generalized model might not perform well on individual clients'
unique data distributions , resulting in poorly trained models.

**3. Client Dissatisfaction :** Since the Global Model is a generalization, it may not represent the specific data characteristics of each client well, causing dissatisfaction among the clients who feel that the global model doesn't perform well for their data.

### Proposed Solutions for the Challenges:

* To address these challenges , two algorithms were proposed called **Fed-Cyclic** and **Fed-Star** .These algorithms aim to better handle the differences in data across clients while still maintaining good overall performance of the global model.
	* **Fed-Cyclic :** 
		* This algorithm involves a cyclic process where each client takes turns updating global model.
		* Each Client's update considers the unique characteristics of its data, reducing the negative impact of averaging heterogenous data.
	* **Fed-Star :** 
		* This algorithm creates a star-shaped communication pattern where the central server coordinated updates but takes into account the specific data distribution of each client.
### Benefits of Fed-Cyclic and Fed-Star:
* **Statistical Heterogeneity Handling :** These algorithms are designed to better manage the differences in data across clients, ensuring that the global model is not just an average nut also considers local variations.

* **Improved Local Performance :** By accounting for local data distributions, these algorithms improve the performance of individual clients' data.

* **Client Satisfaction :**  With a more accurate global model that performs well on their specific data, clients are more likely to be satisfied with the overall federated learning process.

### Dataset Preparation for Office 31 Dataset
#### Overview:
* The Office 31 dataset consists of images representing common office equipment such as keyboards, printers, monitors, laptops, and more. This dataset was used as a model to create our own collection similar images.
  