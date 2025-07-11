# WebSafe Security Scanner

A comprehensive security analysis platform that combines web vulnerability scanning and network threat detection capabilities.

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

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd webvulnscanner
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
webvulnscanner/
├── scanner/                          # Main Django app
│   ├── ml_model/                     # Machine learning models
│   │   ├── model_rf.pkl             # Network threat detection model
│   │   ├── url_classifier.pkl       # URL classification model
│   │   ├── feature_columns.pkl      # Feature columns for ML
│   │   └── label_encoder.pkl        # Label encoder for ML
│   ├── realtime/                     # Network threat detection
│   │   ├── capture.py               # Packet capture functionality
│   │   ├── classifier.py            # ML classification
│   │   └── features.py              # Feature extraction
│   ├── utils/                        # Core utilities
│   │   ├── scanner_core.py          # Web vulnerability scanner
│   │   ├── pdf_generator.py         # PDF report generation
│   │   └── url_classifier.py        # URL classification
│   ├── templates/                    # HTML templates
│   │   └── scanner/
│   │       ├── base.html            # Base template
│   │       ├── home.html            # Web scanner interface
│   │       ├── dashboard.html       # Main dashboard
│   │       └── network_threat_detection.html
│   ├── views.py                      # Django views
│   └── urls.py                       # URL routing
├── websafe/                          # Django project settings
├── requirements.txt                   # Python dependencies
└── manage.py                         # Django management script
```

## 🎯 Usage

### Web Vulnerability Scanner
1. Navigate to the Web Scanner page
2. Enter a URL to scan or upload a CSV file with multiple URLs
3. Click "Start Scan" to begin vulnerability analysis
4. View results with risk levels and detailed findings
5. Download PDF reports for comprehensive documentation

### Network Threat Detection
1. Navigate to the Network Detection page
2. Click "Start Detection" to begin real-time monitoring
3. View live threat detection results and statistics
4. Monitor network traffic for malicious activities
5. Stop detection when finished

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

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Disclaimer

This tool is for educational and authorized security testing purposes only. Users are responsible for ensuring they have proper authorization before scanning any systems or networks.

---

**WebSafe Security Scanner** - Comprehensive Web & Network Security Analysis Platform 