# DISCUSSION & RESULTS ANALYSIS
1. DATA PREPROCESSING:
   - Loaded Fashion-MNIST dataset: 60,000 training + 10,000 test images.
   - Each image is 28x28 pixels, grayscale (same size as MNIST digits).
   - Normalized pixel values from [0,255] to [0,1] for faster convergence.

2. MODEL ARCHITECTURE:
   - Input: 28x28 = 784 features after flattening (same as your MNIST code!).
   - Hidden Layers: Dense(128) → Dense(64) with ReLU activation.
   - Output: Dense(10) with softmax for 10 clothing classes.
   - EXACTLY the same structure as your original MNIST code.

3. TRAINING RESULTS:
   - Trained for 10 epochs with validation_split=0.2.
   - Expected test accuracy: ~87-89% (slightly lower than MNIST digits).
   - Fashion-MNIST is harder than digit MNIST because clothing items have more variation.

4. EVALUATION METRICS:
   - Confusion Matrix: Shows which clothing items get confused.
     * 'Shirt' vs 'T-shirt/top' is commonly confused.
     * 'Coat' vs 'Pullover' can also be tricky.
     * 'Trouser', 'Bag', 'Sandal', 'Ankle boot' are usually easier.
   - Classification Report: Per-class precision, recall, and F1-score.
   - Per-class accuracy shows which items the model struggles with most.

5. COMPARISON WITH MNIST DIGITS:
   - Same image size (28x28), same grayscale format.
   - Same ANN architecture gives ~98% on MNIST digits but ~87-89% on Fashion-MNIST.
   - Why? Clothing items have more intra-class variation than digits.
   - A 'Shirt' can look very different from another 'Shirt' (different styles, patterns).
   - Digits 0-9 have more consistent shapes across samples.

6. WHY SOME CLASSES ARE HARDER:
   - 'Shirt': Often confused with 'T-shirt/top' and 'Pullover'.
   - 'Coat': Similar shape to 'Pullover', hard to distinguish.
   - 'Trouser', 'Bag', 'Sandal': Distinct shapes → easier to classify.
   - 'Sneaker' vs 'Ankle boot': Sometimes confused due to similar footware category.

7. POSSIBLE IMPROVEMENTS:
   - Add Dropout layers (e.g., Dropout(0.2)) to reduce overfitting.
   - Use BatchNormalization for more stable training.
   - Data Augmentation (small rotations, shifts) to increase diversity.
   - Try CNN for better spatial feature extraction (can reach ~93%+).
   - Deeper network or more neurons in hidden layers.

8. KEY TAKEAWAY:
   - Fashion-MNIST is a great "step up" from MNIST digits.
   - Same data format but more realistic complexity.
   - Proves that image shape alone doesn't determine difficulty and that content matters.
