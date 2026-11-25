# AIML (BTECPC602) exam marks sheet

I based this sheet on DBATU ECE papers from Summer 2024, Winter 2024 supplementary, and Summer 2025.

## Paper pattern

- 3 hours, 60 marks.
- Q1: 12 compulsory MCQs (1 mark each).
- Q2 to Q6: attempt any 4 (12 marks each). Each question usually has two 6-mark parts.
- A 6-mark answer needs a definition, 4 to 5 clear points, and an example or diagram where possible. Write a heading for each part.

## Q1 MCQ answer bank

Past-paper questions repeat. Mark the options in this table.

| Question | Correct answer |
| --- | --- |
| Goal of supervised learning | Predictions based on labelled data |
| Episodic environment | Current action does not depend on previous actions |
| Generate and test | Generate possible solutions, then test their validity |
| IDDFS preferred over DFS | DFS space efficiency with BFS completeness |
| Data structure in DFS | Stack |
| Optimal on an unweighted graph | BFS |
| Example of unsupervised learning | K-means clustering |
| Regression metric | Mean Squared Error (MSE) |
| Confusion matrix shows | Actual vs predicted classifications |
| Balances precision and recall | F1 score |
| Objective of linear regression | Minimise the cost function |
| Sigmoid output range | 0 to 1 |
| Main goal of AI | Machines that think and act like humans |
| AI agent | Entity that perceives the environment and acts on it |
| Rational agent in a vacuum world | Move and clean based on percepts |
| Four main agent types | Simple reflex, model-based, goal-based, utility-based |
| Rationality in AI | Act to maximise goal achievement |
| Uses only heuristic h(n) | Greedy best-first search |
| Overfitting | Good training performance, poor test performance |
| Confusion matrix evaluates | Classification models |
| Hill-climbing strategy | Move to the neighbour with the best heuristic value |
| Logistic regression function | Sigmoid |
| Not a classification metric | Mean Squared Error |
| Linear regression cost function | Mean Squared Error |

## Unit 1: AI and agents

**Artificial Intelligence** is the field that makes machines perform tasks that need human intelligence. These tasks include learning, reasoning, perception, and decision making.
Need for AI:

1. Automate repetitive work.
2. Process data that is too large for humans.
3. Work without fatigue.
4. Reduce human error.
5. Assist in diagnosis, robots, and recommendations.

**Strong vs weak AI.** Weak (narrow) AI handles one specific task, such as chess or a chatbot. It has no understanding or consciousness. Strong (general) AI would have human-level reasoning across tasks. It is still hypothetical.

**Stages of AI.** AI is the broad goal. Machine learning is the subset that learns from data without explicit programming. Deep learning is the subset of ML that uses multi-layer neural networks to learn features automatically.
Examples:

1. Rule-based expert system (AI).
2. Linear regression (ML).
3. Image recognition with a CNN (DL).

**Agent** is an entity that perceives its environment through sensors and acts through actuators.
Agent types:

1. Simple reflex: acts on condition-action rules that use only the current percept.
2. Model-based reflex: keeps an internal model of the world to handle partial observability.
3. Goal-based: selects actions that lead to a desired goal.
4. Utility-based: chooses the action that maximises a utility value. This type balances speed, cost, and safety.
5. Learning agent: improves its rules or model from past experience.

**Rational agent** chooses the action that is expected to maximise the performance measure. The choice uses the percepts and prior knowledge.
Environment dimensions: fully or partially observable, deterministic or stochastic, episodic or sequential, static or dynamic, discrete or continuous.
Episodic means that each episode is independent. The current action does not depend on past actions.

## Unit 2: Search

**Heuristic search** uses a heuristic function h(n). The function estimates the cost from node n to the goal. The search explores promising states first and expands fewer nodes.
Example: the 8-puzzle uses Manhattan distance. This is the sum of the distances of each tile from its goal position. A more accurate heuristic expands fewer nodes. It is usually more expensive to compute.

**BFS vs DFS.**

| BFS | DFS |
| --- | --- |
| Uses a queue | Uses a stack |
| Explores level by level | Goes as deep as possible first |
| Complete, and optimal for unweighted graphs | Not complete in infinite spaces, not optimal |
| Memory O(b^d), so it can exhaust memory | Memory O(bd), with low memory use |

Iterative deepening DFS repeats DFS with increasing depth limits. It keeps the low memory use of DFS and the completeness of BFS.

**A* search** uses f(n) = g(n) + h(n). Here g is the cost so far and h is the estimated cost to the goal. The algorithm is complete and optimal when h is admissible. Admissible means that h never overestimates the true cost.
Advantages: optimal, focused, and often efficient.
Disadvantages: high memory use, the need for an admissible heuristic, and slower search when the heuristic is poor.

**Hill climbing** is local search. Start with a solution and move to a neighbour with a better value. Stop when no neighbour improves the solution. Steepest hill climbing evaluates all neighbours and picks the best one.
Failures: local maxima, plateaus, and ridges.
Fixes: random restarts, sideways moves, and simulated annealing.

**Tabu search** is a metaheuristic for combinatorial optimisation. It starts with a solution and explores neighbours. It accepts the best move even when that move makes the solution worse for a short time. This step helps the search escape local optima. A tabu list records recent moves or attributes. The list forbids reversing them for a set number of iterations, so cycles cannot occur. An aspiration criterion allows a tabu move when it gives a solution better than any found so far. The search stops after a maximum number of iterations or after no improvement.
Applications: scheduling, routing, and the travelling salesman problem.

**Generate and test.** Generate candidate solutions. Then test each one against the goal condition.

**Alpha-beta pruning** cuts branches of the minimax tree that cannot affect the final decision. It uses alpha (best value for MAX) and beta (best value for MIN). It gives the same result as minimax with less computation. Move ordering, with the best moves first, improves pruning.

## Unit 3: Machine learning basics

**Types of machine learning.**

1. Supervised: uses labelled data to learn an input-to-output mapping. Classification gives discrete labels. Regression gives continuous values.
2. Unsupervised: uses unlabelled data to find hidden structure. Examples: clustering (K-means), dimensionality reduction (PCA), and association rules.
3. Reinforcement: an agent learns from rewards and penalties that follow its actions in an environment.
4. Semi-supervised: uses a small labelled set and a larger unlabelled set.

**Classification vs regression.** Classification predicts a category, such as spam or not spam. It uses accuracy, precision, recall, F1, and a confusion matrix. Regression predicts a continuous number, such as a house price. It uses MSE, MAE, and R squared.

**Decision tree.** A tree has a root, internal nodes that test a feature, branches for the outcomes, and leaves that hold the prediction. The algorithm chooses splits by information gain (entropy reduction) or the Gini index.
Example: predict "play tennis" from outlook and humidity. If outlook is overcast, answer yes. If outlook is sunny and humidity is high, answer no.
Advantages: easy to interpret and little data preparation.
Disadvantages: the tree overfits easily and is unstable under small data changes.

**Inductive bias** is the set of assumptions that a learning algorithm uses to generalise beyond its training examples. It is necessary because a finite dataset cannot identify one correct hypothesis.
Examples:

1. Prefer a simpler hypothesis.
2. Assume a linear boundary.
3. Assume smooth variation.

Without bias, generalisation is impossible.

**Overfitting** means that the model fits training noise as well as the pattern. Training accuracy is high and test accuracy is low. Prevent overfitting with more data, regularisation, pruning, early stopping, and cross-validation.

**Cross-validation** gives a more reliable performance estimate and supports model selection. In k-fold cross-validation:

1. Split the data into k equal parts.
2. Train on k-1 parts and test on the remaining part.
3. Repeat for every part and average the scores.

Leave-one-out uses k equal to the number of samples. Stratified k-fold keeps the same class proportion in each fold.

**Ensemble learning** combines several models to improve accuracy and reduce variance or bias. Bagging trains models on bootstrap samples and averages them, as in random forest. Boosting trains models in sequence. Each model corrects earlier errors, as in AdaBoost and gradient boosting.

**K-means clustering** chooses k centroids and assigns each point to the nearest centroid. It recomputes the centroids and repeats until the assignments stop changing. You must choose k in advance. The result depends on the initial centroids.

## Unit 4: Evaluation metrics

**Confusion matrix** is a table of actual versus predicted classes. It has four cells: true positive (TP), true negative (TN), false positive (FP), and false negative (FN).

- Accuracy = (TP + TN) / (TP + TN + FP + FN)
- Precision = TP / (TP + FP)
- Recall (sensitivity) = TP / (TP + FN)
- Specificity = TN / (TN + FP)
- F1 = 2 x Precision x Recall / (Precision + Recall)

Accuracy misleads when classes are imbalanced. Use F1 when the positive class matters and both false positives and false negatives have a cost.

**AUC-ROC vs F1.** The ROC curve plots the true positive rate against the false positive rate across thresholds. AUC is the area under the curve. A value of 1 is perfect and 0.5 is random. AUC does not depend on the threshold and works well for imbalanced data and ranking. F1 is the harmonic mean of precision and recall at one chosen threshold. It suits a fixed operating point where the positive class matters. Use AUC to compare models. Use F1 to report performance at the threshold you will use.

**Regression metrics.** MSE is the average squared error. MAE is the average absolute error. RMSE is the square root of MSE. R squared = 1 - SS_res / SS_tot. It gives the fraction of variance explained by the model. It is 1 for a perfect fit and 0 for a model no better than predicting the mean. Adjusted R squared penalises extra features.

## Unit 5: Regression and gradient descent

**Linear regression** models y = b0 + b1 x for one feature. For multiple features it models y = b0 + b1 x1 + ... + bn xn. The cost function is J = (1/2m) sum of (predicted - actual)^2, which is mean squared error.
Types: simple linear, multiple (multivariable) linear, and polynomial regression.
You find the parameters by minimising the cost with gradient descent or the normal equation.

**Gradient descent** updates parameters in the direction opposite to the gradient. Use theta = theta - alpha x (derivative of J with respect to theta), where alpha is the learning rate. Repeat until the cost converges.
Variants:

1. Batch: uses the whole dataset per step, so it is accurate but slow and memory heavy.
2. Stochastic: uses one sample per step, so it is fast and noisy.
3. Mini-batch: uses small batches, which is a compromise between the two.

**Logistic regression** predicts a probability with the sigmoid function, p = 1 / (1 + e^(-z)). The output lies between 0 and 1. The cost function is cross-entropy (log loss): -[ y log(p) + (1-y) log(1-p) ]. Classify with a threshold, usually 0.5. Despite its name, logistic regression is a classification method.

scikit-learn implementation:

```python
from sklearn.linear_model import LogisticRegression
model = LogisticRegression()
model.fit(X_train, y_train)
predictions = model.predict(X_test)
probabilities = model.predict_proba(X_test)[:, 1]
```

**Linear vs logistic regression.** Linear regression outputs a continuous value, uses MSE, and fits a line or hyperplane. Logistic regression outputs a probability between 0 and 1, uses the sigmoid function and cross-entropy loss, and performs classification.

## How to use this tomorrow

1. Learn the MCQ table first. It gives 12 marks.
2. Memorise the Tabu search, agent types, confusion matrix formulas, and BFS versus DFS table. These recur every year.
3. For each 6-mark part, write the definition, then 4 to 5 points, then a small example. This usually earns full marks in these papers.
4. Attempt the questions whose answers you know first. Tabu search and agents are the safest 12-mark choices.

## Writing tips for the exam

**Time budget.** You have 3 hours and 60 marks. Give about 10 minutes to Q1. Give about 25 to 28 minutes to each 12-mark question. Keep the last 10 minutes for the check. Five answered questions beat three perfect ones.

**Order.** Start with the question you know best, not necessarily Q2. Write the question number and part label (A or B) at the top of each answer.

**Structure of a 6-mark answer.** Write a one-line definition first. Then write 4 to 5 numbered points. Then add an example or diagram. Keep each point to one or two lines on a new line. Underline key terms such as "admissible", "tabu list", and "precision" so the examiner can spot them.

**Diagrams and tables.** Draw them where they help: a tree for a decision tree, a state-space graph for search, a confusion matrix as a 2 by 2 table, and a block diagram for an agent. Label every box, arrow, and axis. A labelled diagram can earn marks on its own.

**Formulas.** Write the full formula and define each symbol. For example, with Precision = TP / (TP + FP), say what TP and FP mean. With f(n) = g(n) + h(n), say what g and h are. Do not write only the final number for a metric question.

**Show steps.** In any calculation, write the given values, the formula, the substitution, and the result. Examiners often award step marks even when the final answer is wrong.

**If you are unsure.** Write the definition and every related point you remember. The paper does not mention negative marking. A partial answer is better than a blank page. Do not spend more than a minute on one part. Move to another part. Return later.

**Presentation.** Write legibly. Leave a line between answers. Use a pen. Cross out mistakes with a single line. Do not scribble. The paper says to assume suitable data where needed. State your assumption in one line before solving.

**Final check.** Check that all 12 MCQs are answered. Check that you attempted exactly 4 of Q2 to Q6. Check that both parts of each chosen question are present.

## Full-marks answer bank

Learn these answers. Write them with the heading, the numbered points, and the example. Each one covers a 6-mark part.

**1. Define AI and state the need for AI.**
Artificial Intelligence is the field that makes machines perform tasks that need human intelligence. These tasks include learning, reasoning, perception, and decision making.
Give these points:

1. AI automates repetitive work and reduces human effort.
2. AI processes large data sets faster than a human can.
3. AI works without fatigue and gives consistent results.
4. AI reduces human error in diagnosis and design.
5. AI supports robots, recommendations, and speech systems.

Example: a rule-based expert system diagnoses a fault from the symptoms that the user enters.

**2. What is an agent? State the types of agent programs.**
An agent is an entity that perceives its environment through sensors and acts through actuators.
Agent programs:

1. Simple reflex: uses condition-action rules on the current percept.
2. Model-based reflex: keeps an internal model of the world.
3. Goal-based: selects actions that reach a goal.
4. Utility-based: selects the action with the highest utility value.
5. Learning agent: updates its rules or model from experience.

A rational agent selects the action that is expected to maximise the performance measure. Example: a vacuum agent moves and cleans when its sensor detects dust.

**3. Differentiate between BFS and DFS.**
BFS explores a state space level by level. DFS explores one branch to its deepest point before it moves to another branch.

1. BFS uses a queue. DFS uses a stack.
2. BFS is complete on finite graphs. DFS can follow an infinite path.
3. BFS is optimal on an unweighted graph. DFS is not optimal.
4. BFS uses O(b^d) memory. DFS uses O(bd) memory.
5. Iterative deepening DFS repeats DFS with depth limits. It keeps the low memory use of DFS and the completeness of BFS.

Example: on a tree with branching factor 2 and a solution at depth 3, BFS expands all nodes at depth 2 before it expands nodes at depth 3.

**4. Explain heuristic search with an example.**
A heuristic function h(n) estimates the cost from node n to the goal. Heuristic search expands nodes with the best estimated cost first.

1. The heuristic guides the search toward promising states.
2. A more accurate heuristic expands fewer nodes.
3. A more accurate heuristic is usually harder to compute.
4. A* uses f(n) = g(n) + h(n). Here g is the cost so far.
5. A* is optimal when h is admissible. Admissible means that h never overestimates the true cost.

Example: the 8-puzzle uses Manhattan distance. This is the sum of the distances of the tiles from their goal positions.

**5. Explain Tabu search in detail.**
Tabu search is a metaheuristic for combinatorial optimisation. It starts with a solution and moves to the best neighbour.

1. It accepts a worse move when that move helps it escape a local optimum.
2. A tabu list stores recent moves or attributes.
3. The tabu list forbids reversing a recent move for a set number of iterations. This step prevents cycles.
4. An aspiration criterion permits a tabu move when it gives a solution better than any found so far.
5. The search stops after a maximum number of iterations or after no improvement.

Example: use Tabu search for job scheduling or for the travelling salesman problem.

**6. Explain hill climbing and steepest hill climbing.**
Hill climbing is a local search method. It starts with a solution and moves to a neighbour with a better value.

1. Plain hill climbing takes the first better neighbour that it finds.
2. Steepest hill climbing evaluates all neighbours and takes the best one.
3. The search stops when no neighbour improves the solution.
4. It can stop at a local maximum, a plateau, or a ridge.
5. Random restarts and sideways moves help it escape these points.

Example: in the 8-queens problem, move one queen to reduce the number of attacks.

**7. Explain the types of machine learning.**

1. Supervised learning uses labelled data. It learns a mapping from input to output. Classification gives discrete labels. Regression gives continuous values.
2. Unsupervised learning uses unlabelled data. It finds hidden structure. Examples are K-means clustering and PCA.
3. Reinforcement learning uses rewards and penalties. An agent improves its actions from the feedback.
4. Semi-supervised learning uses a small labelled set and a larger unlabelled set.

Example: predict house price from area with linear regression (supervised). Group customers by buying habit with K-means (unsupervised).

**8. Explain a decision tree with an example.**
A decision tree has a root, internal nodes, branches, and leaves.

1. Each internal node tests a feature.
2. Each branch is an outcome of the test.
3. Each leaf holds the predicted class or value.
4. The algorithm chooses splits by information gain or the Gini index.
5. The tree is easy to read, but it can overfit.

Example: predict "play tennis" from outlook and humidity. If outlook is overcast, answer yes. If outlook is sunny and humidity is high, answer no.

**9. Explain inductive bias and cross-validation.**
Inductive bias is the set of assumptions that a learner uses to generalise beyond its training examples. A finite dataset cannot identify one correct hypothesis, so bias is necessary.
Examples of bias: prefer a simpler hypothesis, assume a linear boundary, and assume smooth variation.
Cross-validation gives a reliable performance estimate.

1. In k-fold cross-validation, split the data into k equal parts.
2. Train on k-1 parts and test on the remaining part.
3. Repeat for every part and average the scores.
4. Leave-one-out uses k equal to the number of samples.
5. Stratified k-fold keeps the same class proportion in each fold.

Overfitting means high training accuracy and low test accuracy. Cross-validation helps detect it.

**10. Explain the confusion matrix and classification metrics.**
A confusion matrix is a table of actual versus predicted classes. It has four cells: TP, TN, FP, and FN.

1. Accuracy = (TP + TN) / (TP + TN + FP + FN).
2. Precision = TP / (TP + FP).
3. Recall = TP / (TP + FN).
4. Specificity = TN / (TN + FP).
5. F1 = 2 x Precision x Recall / (Precision + Recall).

Accuracy misleads when classes are imbalanced. Use F1 when the positive class matters. Example: with 90 negative cases and 10 positive cases, a model that predicts "negative" every time has 90% accuracy and zero recall.

**11. Compare AUC-ROC and F1. Also state regression metrics.**
The ROC curve plots the true positive rate against the false positive rate at different thresholds. AUC is the area under that curve. A value of 1 is perfect and 0.5 is random. AUC does not depend on a threshold and suits imbalanced data. F1 is the harmonic mean of precision and recall at one threshold. Use F1 to report performance at the threshold you will use.
Regression metrics:

1. MSE is the average squared error.
2. MAE is the average absolute error.
3. RMSE is the square root of MSE.
4. R squared = 1 - SS_res / SS_tot. It gives the fraction of variance explained by the model.

**12. Explain linear regression, gradient descent, and logistic regression.**
Linear regression models y = b0 + b1 x. The cost function is mean squared error. You find the parameters by minimising the cost.
Gradient descent updates parameters with theta = theta - alpha x (derivative of J with respect to theta). Alpha is the learning rate.

1. Batch uses the whole dataset per step. It is accurate but slow.
2. Stochastic uses one sample per step. It is fast but noisy.
3. Mini-batch uses small batches. It balances speed and accuracy.

Logistic regression predicts a probability with the sigmoid function, p = 1 / (1 + e^(-z)). The output lies between 0 and 1. The cost is cross-entropy. Use a threshold of 0.5 to classify.
In sklearn: create LogisticRegression(), call fit(X_train, y_train), then call predict(X_test).

