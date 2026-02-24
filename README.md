# 🌸 Iris Flower Classifier App 🌸

A beautiful machine learning application built with KivyMD that classifies iris flowers into three species (Setosa, Versicolor, Virginica) based on their physical measurements. The app features an intuitive Material Design 3 interface with real-time prediction capabilities and comprehensive input validation.

## Features

- **Real-time Classification**: Instant iris species prediction
- **Input Validation**: Smart validation with error highlighting
- **Auto Data Loading**: Automatically loads iris dataset or falls back to sklearn
- **Material Design 3**: Modern, clean interface with purple theme
- **Error Handling**: User-friendly error dialogs and input validation
- **Interactive Image**: Visual iris flower reference
- **Scrollable Interface**: Optimized for various screen sizes
- **Clear Functionality**: Easy input reset with one tap

## Screenshots

The app features a single, comprehensive screen with:
- **Header**: Beautiful iris flower image and title
- **Input Fields**: Four measurement input fields with validation
- **Action Buttons**: Predict and Clear functionality
- **Results Display**: Large, clear prediction output
- **Error Dialogs**: Informative error messages

## Machine Learning Model

- **Algorithm**: Random Forest Classifier
- **Features**: Sepal Length, Sepal Width, Petal Length, Petal Width
- **Species**: Setosa, Versicolor, Virginica
- **Accuracy**: ~95-98% on test data
- **Training**: 80% of dataset used for training

## Requirements

### Python Dependencies
```
kivymd>=1.1.1
kivy>=2.1.0
scikit-learn>=1.2.0
pandas>=1.5.0
```

### System Requirements
- Python 3.8 or higher
- Android 5.0+ (for mobile deployment)
- 512MB RAM minimum
- 25MB storage space

## Installation

1. Clone this repository:
```bash
git clone <your-repo-url>
cd iris-classifier-app
```

2. Install required dependencies:
```bash
pip install kivymd scikit-learn pandas
```

3. Run the application:
```bash
python main.py
```

## Usage

### 1. Input Measurements
Enter the flower measurements in centimeters:
- **Sepal Length**: Length of the sepal (outer part)
- **Sepal Width**: Width of the sepal
- **Petal Length**: Length of the petal (inner part) 
- **Petal Width**: Width of the petal

### 2. Validate Input
- All values must be between 0.1 and 10.0 cm
- Only numeric values are accepted
- Invalid inputs are highlighted in red
- Helper text appears for guidance

### 3. Get Prediction
- Tap "Predict Species" to classify the flower
- Results appear instantly below the buttons
- Species name is displayed in proper case

### 4. Clear and Retry
- Use "Clear" button to reset all inputs
- All error states are cleared
- Ready for new prediction

## Input Ranges

| Measurement | Typical Range | Unit |
|-------------|---------------|------|
| Sepal Length | 4.3 - 7.9 | cm |
| Sepal Width | 2.0 - 4.4 | cm |
| Petal Length | 1.0 - 6.9 | cm |
| Petal Width | 0.1 - 2.5 | cm |

### Example Measurements

**Iris Setosa:**
- Sepal Length: 5.1 cm
- Sepal Width: 3.5 cm  
- Petal Length: 1.4 cm
- Petal Width: 0.2 cm

**Iris Versicolor:**
- Sepal Length: 7.0 cm
- Sepal Width: 3.2 cm
- Petal Length: 4.7 cm
- Petal Width: 1.4 cm

**Iris Virginica:**
- Sepal Length: 6.3 cm
- Sepal Width: 3.3 cm
- Petal Length: 6.0 cm
- Petal Width: 2.5 cm

## Data Sources

### Primary Data Source
- **iris.csv**: Custom CSV file (if available)
- Place in the same directory as main.py

### Fallback Data Source
- **Sklearn Dataset**: Built-in iris dataset from scikit-learn
- Automatically loads if iris.csv is not found
- Contains 150 samples across 3 species

### CSV Format (if using custom file)
```csv
sepal_length,sepal_width,petal_length,petal_width,species
5.1,3.5,1.4,0.2,setosa
4.9,3.0,1.4,0.2,setosa
7.0,3.2,4.7,1.4,versicolor
...
```

## Model Architecture

### Data Processing Pipeline
1. **Data Loading**: CSV or sklearn dataset
2. **Feature Selection**: 4 numeric measurements
3. **Label Encoding**: Species names to numeric values
4. **Data Splitting**: 80% training, 20% testing
5. **Feature Scaling**: StandardScaler normalization
6. **Model Training**: Random Forest with 100 estimators

### Model Performance
- **Algorithm**: Random Forest Classifier
- **Estimators**: 100 trees
- **Random State**: 42 (reproducible results)
- **Expected Accuracy**: 95-98%
- **Training Time**: < 1 second

## UI Components

### Input Fields
- **Type**: MDTextField with rectangle mode
- **Validation**: Real-time input filtering
- **Error States**: Visual feedback for invalid input
- **Helper Text**: Contextual guidance

### Buttons
- **Predict Button**: Primary action in purple theme
- **Clear Button**: Secondary action for reset
- **Responsive Design**: Adapts to screen size

### Visual Elements
- **Iris Image**: Educational reference from Python repository
- **Material Design 3**: Modern design language
- **Purple Theme**: Elegant color scheme
- **Scrollable Layout**: Accommodates various screen sizes

## Error Handling

### Input Validation Errors
- **Empty Fields**: Required field validation
- **Invalid Numbers**: Non-numeric input detection
- **Out of Range**: Values outside 0.1-10.0 range
- **Visual Feedback**: Red highlighting and helper text

### System Errors
- **File Loading**: Graceful fallback to sklearn dataset
- **Model Training**: Comprehensive error dialog
- **Prediction Errors**: User-friendly error messages
- **Network Issues**: Handles image loading failures

## Troubleshooting

### Common Issues

**"Error loading or training model"**
- Check if iris.csv is properly formatted
- Ensure sklearn is installed correctly
- Verify Python version compatibility

**"Invalid input" errors**
- Enter only numeric values (use decimal point, not comma)
- Stay within 0.1-10.0 cm range
- Fill all four measurement fields

**App won't start**
- Install all required dependencies
- Check Python version (3.8+)
- Verify KivyMD installation

**Prediction seems wrong**
- Double-check measurement accuracy
- Compare with example measurements
- Ensure measurements are in centimeters

**Image not loading**
- Check internet connection
- Image will show placeholder if unavailable
- Functionality works without image

## Performance

- **Startup Time**: 2-3 seconds (model training)
- **Prediction Time**: < 100ms per prediction
- **Memory Usage**: ~30-50MB
- **Model Size**: < 1MB
- **Supported Predictions**: Unlimited

## Mobile Deployment

### Android APK Build

1. Install Buildozer:
```bash
pip install buildozer
```

2. Initialize buildozer:
```bash
buildozer init
```

3. Edit buildozer.spec requirements:
```
requirements = python3,kivy,kivymd,scikit-learn,pandas,numpy
```

4. Build APK:
```bash
buildozer android debug
```

### iOS Deployment
- Use kivy-ios for iOS builds
- Additional Xcode setup required
- Follow KivyMD iOS deployment guide

### Changing Themes
```python
# In IrisClassifierApp.build()
self.theme_cls.primary_palette = "Blue"  # Change color
self.theme_cls.theme_style = "Dark"      # Dark/Light mode
```

### Adding New Features
- **Confidence Scores**: Display prediction probability
- **Multiple Models**: Compare different algorithms
- **Data Visualization**: Add charts and graphs
- **Export Results**: Save predictions to file

### Model Improvements
- **Cross-validation**: Better performance estimation
- **Hyperparameter Tuning**: Optimize model parameters
- **Feature Engineering**: Add derived features
- **Ensemble Methods**: Combine multiple models

## Scientific Background

### Iris Dataset
- **Created by**: Ronald Fisher (1936)
- **Species Count**: 3 (Setosa, Versicolor, Virginica)
- **Sample Size**: 50 per species (150 total)
- **Features**: 4 morphological measurements
- **Use Case**: Classification benchmark dataset

### Flower Anatomy
- **Sepals**: Outer protective structures
- **Petals**: Inner colorful structures
- **Measurements**: Length and width in centimeters
- **Distinction**: Key differences between species

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow Material Design 3 principles
- Maintain input validation standards
- Add comprehensive error handling
- Test on multiple screen sizes
- Document new features

## Future Enhancements

- [ ] **Camera Integration**: Classify from flower photos
- [ ] **Offline Mode**: Work without internet connection
- [ ] **Batch Processing**: Multiple flower classification
- [ ] **Learning Mode**: Educational content about iris species
- [ ] **Statistics Dashboard**: Model performance metrics
- [ ] **Export Functionality**: Save results to CSV/PDF
- [ ] **Voice Input**: Speak measurements instead of typing
- [ ] **Multi-language Support**: Localization features

