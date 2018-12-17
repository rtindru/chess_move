# chess_move
Chess Piece Detector

### Data
The data was created manually by screenshotting and cropping various chess piece and board
designs from lichess.org, chess.com, chess24.com. The dataset consists of 1k images based of
the 2D chess boards on online chess websites.

A total of 35-40 designs of chess boards was used. The dataset has images that vary in
background, texture, shape, color, and design. This variability is a close approximation to online
chess boards that the model is meant to cope with - online and on-screen 2D chess boards on
popular chess sites.

The dataset will be used for both training, validation and testing of the model. Variability in zoom,
shear, and rotation is introduced during training and testing using keras. The dataset is organized
into 6 subdirectories based of the different classes of the chess pieces. K for king, Q for queen, N
for knign, B for bishop, R for rook, P for pawn, and B for blank. Blank is treated as a separate class
since it overall fits nicely into the multi-class classification paradigm. It is equally possible to
exclude the blank class and use a rule-based system to classify it beforehand.

The dataset is well balanced, with equal number of images for most classes. However, the queen
and king classes have fewer images - this is simply a function of the fact that there is only one set
of king & queen per board, whereas two sets of all other pieces. The number of pawns has
purposefully been limited so as to not introduce imbalance in the dataset. Here are a few of the
images from the dataset.

#### Directories
The directory structure is as follows

- data
  - data_new: train data for all model training + validation
    - BISHOP: test images of bishop
    - BLANK: test images of blank cells
    - KING: test images of king
    - KNIGHT: test images of knight
    - PAWN: test images of pawn
    - QUEEN: test images of queen
    - ROOK: test images of rook
  - data_test: test data for model accuracy and metrics
    - BISHOP: ...
    - ...

#### Image Properties
- All images are 64x64 pixels
- All images have been converted to grayscale
- Colors are not differentiated. Both black and white pieces are together in the same directory per piece

### Packages

#### Base Model
The base model uses scikitlearn for the model + evaluation steps. We use a SVM, PCA, and GridSearchCV.

#### Deep Neural Net
The Deep Neural Network used Keras with a Tensorflow backend. The tensorflow backend is GPU enabled. We use tensorflow 1.12 with Cuda9.0 and CuDNN7

#### Package List
Refer conda.txt 
