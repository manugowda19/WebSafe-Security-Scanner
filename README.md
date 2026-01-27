# WebSafe Security Scanner -- V1

A comprehensive security analysis platform that combines web vulnerability scanning and network threat detection capabilities. 

- Youtube video :-  [click here](https://youtu.be/SwOTjGKdNz4)
- In case you cannot download the file you can download it from the drive :- [click here](https://drive.google.com/drive/folders/1ypQ5_xgWa9YRA7nQUgnY32wMeuzBLVwj?usp=sharing)
- Before running the file do make sure to unzip the zip file 

## 🚀 Features

### Web Vulnerability Scanner
- **SQL Injection Detection**: Automated testing for SQL injection vulnerabilities
- **Cross-Site Scripting (XSS)**: Detection of XSS vulnerabilities
- **CSRF Protection**: Analysis of CSRF protection mechanisms
- **Security Headers**: Assessment of security headers implementation
- **ML-based URL Classification**: Machine learning model to classify URLs as malicious or benign
- **PDF Report Generation**: Detailed security reports in PDF format

### Network Threat Detection
- **Real-time Packet Analysis**: Live network traffic monitoring
- **DDoS Attack Detection**: Identification of distributed denial of service attacks
- **Port Scanning Detection**: Detection of port scanning activities
- **Anomaly Detection**: AI/ML-based traffic anomaly identification
- **Traffic Flow Analysis**: Comprehensive network flow analysis
- **Threat Classification**: Machine learning-based threat classification with confidence scores

<img width="1325" height="792" alt="Screenshot 2025-07-12 at 11 50 27 AM" src="https://github.com/user-attachments/assets/d6de4659-8f09-442b-96e2-dfd08a611b7d" />

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd webvulnscanner_file
   ```

2. **Create and activate virtual environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run database migrations**
   ```bash
   python3 manage.py migrate
   ```

5. **Start the development server**
   ```bash
   python3 manage.py runserver
   ```

6. **Access the application**
   - Open your browser and go to `http://localhost:8000`
   - Navigate to the Dashboard to see both web and network security features

## 📁 Project Structure

```
webvulnscanner_file/
├── db.sqlite3                  # SQLite database for Django project data
├── manage.py                   # Django management script (runserver, migrations, etc.)
├── README.md                   # Project overview and instructions
├── requirements.txt            # Python dependencies for the project
├── scanner/
│   ├── __init__.py             # Marks this directory as a Python package
│   ├── admin.py                # Django admin interface configuration for scanner app
│   ├── apps.py                 # App configuration for scanner
│   ├── migrations/
│   │   └── __init__.py         # Marks migrations as a Python package
│   ├── ml_model/
│   │   ├── feature_columns.pkl # Saved feature column names for ML model
│   │   ├── label_encoder.pkl   # (Likely) label encoder for ML model (not used in train_model.py)
│   │   ├── model_rf.pkl        # (Likely) Random Forest model (not used in train_model.py)
│   │   ├── train_model.py      # Trains and saves a URL classifier ML model
│   │   └── url_classifier.pkl  # Saved trained URL classifier model
│   ├── models.py               # Django models (database schema) for scanner app
│   ├── realtime/
│   │   ├── __init__.py         # Marks realtime as a Python package
│   │   ├── capture.py          # (Likely) Captures network traffic in real time
│   │   ├── classifier.py       # (Likely) Classifies real-time network data
│   │   └── features.py         # (Likely) Feature extraction for real-time data
│   ├── static/
│   │   └── scanner/
│   │       └── style.css       # CSS styles for scanner app web pages
│   ├── templates/
│   │   └── scanner/
│   │       ├── base.html       # Base HTML template for scanner app
│   │       ├── dashboard.html  # Dashboard page template
│   │       ├── home.html       # Home page template
│   │       └── ...             # (Other HTML templates)
│   ├── tests.py                # Unit tests for scanner app
│   ├── urls.py                 # URL routing for scanner app
│   ├── utils/
│   │   ├── __init__.py         # Marks utils as a Python package
│   │   ├── network_demo.py     # (Likely) Demo for network monitoring
│   │   ├── network_monitor.py  # (Likely) Monitors network activity
│   │   ├── pdf_generator.py    # (Likely) Generates PDF reports
│   │   └── ...                 # (Other utility scripts)
│   └── views.py                # Django views (web request handlers) for scanner app
├── training_set_with_dataset/
│   ├── live_network_analysis/
│   │   ├── dataset/
│   │   │   └── cicids2017_cleaned.csv # Network analysis dataset
│   │   └── Train_Model.ipynb          # Jupyter notebook for training network analysis model
│   └── malicus_link/
│       ├── dataset/
│       │   └── malicious_phish.csv    # Malicious URL dataset
│       └── Malicious_URL_Detection_System.ipynb # Jupyter notebook for URL detection
├── venv/                      # Python virtual environment (dependencies, binaries, etc.)
│   └── ...                    # (Standard venv structure)
└── websafe/
    ├── __init__.py            # Marks websafe as a Python package
    ├── asgi.py                # ASGI config for Django (async server)
    ├── settings.py            # Django project settings
    ├── urls.py                # URL routing for the whole project
    └── wsgi.py                # WSGI config for Django (web server)
```

## 🎯 Usage

### Web Vulnerability Scanner
1. Navigate to the Web Scanner page
2. Enter a URL to scan or upload a CSV file with multiple URLs(for more test csv files [click here](https://drive.google.com/drive/folders/1ypQ5_xgWa9YRA7nQUgnY32wMeuzBLVwj?usp=sharing)
3. Click "Start Scan" to begin vulnerability analysis
4. View results with risk levels and detailed findings
5. Download PDF reports for comprehensive documentation
<img width="1325" height="725" alt="Screenshot 2025-07-12 at 11 51 45 AM" src="https://github.com/user-attachments/assets/5d0e73ca-a64b-4176-acef-a797bcf667ba" />

### Network Threat Detection
1. Navigate to the Network Detection page
2. Click "Start Detection" to begin real-time monitoring
3. View live threat detection results and statistics
4. Monitor network traffic for malicious activities
5. Stop detection when finished
<img width="1328" height="780" alt="Screenshot 2025-07-12 at 11 53 42 AM" src="https://github.com/user-attachments/assets/707ee972-4f65-43f0-a749-e8b326847d1e" />

### Dashboard
- Access the main dashboard for an overview of both systems
- Quick access to all features
- System statistics and feature descriptions

## 🔧 Configuration

### Network Detection Settings
- The system automatically detects the most active network interface
- Manual interface selection available in the capture module
- Adjustable timeout settings for flow analysis

### ML Model Configuration
- Models are automatically loaded from the `ml_model/` directory
- Feature columns and label encoders are included
- Models trained on CICIDS2017 dataset for network threat detection

## 📊 Dependencies

### Core Dependencies
- **Django 4.0+**: Web framework
- **Scikit-learn**: Machine learning models
- **Pandas & NumPy**: Data processing
- **Scapy**: Network packet capture
- **Requests**: HTTP requests for web scanning
- **BeautifulSoup4**: HTML parsing
- **ReportLab**: PDF report generation

### Network Security
- **Scapy**: Packet capture and analysis
- **Joblib**: Model serialization
- **Threading**: Concurrent processing

### Web Security
- **Requests**: HTTP client for vulnerability testing
- **BeautifulSoup4**: HTML parsing for XSS detection
- **ReportLab**: PDF generation for reports

## 🚨 Security Considerations

- **Network Monitoring**: Requires administrative privileges for packet capture
- **Model Security**: ML models should be validated before production use
- **Data Privacy**: Ensure compliance with data protection regulations
- **Access Control**: Implement proper authentication for production deployment

## 🔍 Troubleshooting

### Common Issues

1. **Permission Denied for Network Capture**
   - Run with administrative privileges
   - Check network interface permissions

2. **Model Loading Errors**
   - Ensure all model files are in `scanner/ml_model/`
   - Check file permissions

3. **Django Import Errors**
   - Verify virtual environment activation
   - Check installed dependencies

### Debug Mode
Enable Django debug mode for detailed error messages:
```python
# settings.py
DEBUG = True
```

## 📈 Future Enhancements

- [ ] Real-time dashboard with live statistics
- [ ] API endpoints for external integration
- [ ] Advanced threat intelligence feeds
- [ ] Custom rule creation for threat detection
- [ ] Integration with SIEM systems
- [ ] Mobile application support
- [ ] Cloud deployment options

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## ⚠️ Disclaimer

This tool is for educational and authorized security testing purposes only. Users are responsible for ensuring they have proper authorization before scanning any systems or networks.

---

**WebSafe Security Scanner** - Comprehensive Web & Network Security Analysis Platform 
