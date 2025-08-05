# PayrollPro - Employee Payroll Management System

## Overview

PayrollPro is a comprehensive web-based payroll management system built with Flask that handles employee data management, payroll calculations, and automated communications. The system provides a complete solution for managing employee records, generating payslips, calculating statutory deductions, and distributing payroll information via email.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: Bootstrap 5.3.0 with custom CSS styling
- **UI Components**: Responsive dashboard with card-based layout
- **Styling**: Modern gradient design with CSS custom properties
- **Icons**: Font Awesome 6.4.0 for consistent iconography
- **Charts**: Chart.js for data visualization
- **Templates**: Jinja2 templating engine (Flask default)

### Backend Architecture
- **Framework**: Flask (Python web framework)
- **Architecture Pattern**: Monolithic application with single-file structure
- **Session Management**: Flask sessions with configurable secret key
- **File Handling**: Werkzeug utilities for secure file uploads
- **Logging**: Python's built-in logging module with DEBUG level

### Data Storage
- **Database**: SQLite3 (embedded database)
- **Database File**: `payroll.db` stored locally
- **Schema**: Employee records with comprehensive payroll fields
- **Data Processing**: Pandas for Excel/CSV file operations

## Key Components

### Employee Management
- Employee registration and profile management
- Bulk import functionality via Excel/CSV uploads
- Comprehensive employee data including CTC, PF options, and personal details
- Employee ID-based unique identification system

### Payroll Processing
- Automated salary calculations with statutory deductions
- PF (Provident Fund) calculations based on employee opt-in
- Tax calculations and other deductions
- Monthly and annual CTC management

### Document Generation
- PDF payslip generation using ReportLab
- Professional document formatting with tables and styling
- Automated report generation capabilities
- File download functionality for generated documents

### Email Integration
- SMTP-based email system for payslip distribution
- Support for email attachments (PDF payslips)
- Bulk email capabilities for payroll distribution
- Email configuration through environment variables

### File Management
- Secure file upload handling with size restrictions (16MB max)
- Upload directory management with automatic creation
- Support for Excel and CSV file formats
- File validation and security measures

## Data Flow

1. **Employee Onboarding**: Manual entry or bulk import via Excel/CSV files
2. **Data Storage**: Employee information stored in SQLite database
3. **Payroll Calculation**: Automated calculations based on CTC and deductions
4. **Document Generation**: PDF payslips created using employee and payroll data
5. **Email Distribution**: Automated email delivery of payslips to employees
6. **Dashboard Analytics**: Real-time data visualization and reporting

## External Dependencies

### Python Libraries
- **Flask**: Web framework and routing
- **Pandas**: Data manipulation and Excel/CSV processing
- **ReportLab**: PDF generation and document creation
- **SQLite3**: Database operations (built-in Python module)
- **smtplib**: Email sending capabilities (built-in Python module)
- **Werkzeug**: File handling utilities

### Frontend Libraries
- **Bootstrap 5.3.0**: CSS framework and responsive design
- **Font Awesome 6.4.0**: Icon library
- **Chart.js**: Data visualization and charting

### Email Service
- **SMTP Server**: Configurable email service integration
- **Email Authentication**: Username/password or app-specific passwords
- **File Attachments**: Support for PDF payslip attachments

## Deployment Strategy

### Environment Configuration
- **Session Secret**: Configurable via `SESSION_SECRET` environment variable
- **Upload Directory**: Automatic creation of `uploads` folder
- **Database**: SQLite file created automatically on first run
- **Email Settings**: SMTP configuration through environment variables

### File Structure
- **Static Files**: CSS, JavaScript, and other assets served via Flask
- **Templates**: HTML templates in `templates/` directory
- **Uploads**: User-uploaded files stored in `uploads/` directory
- **Database**: SQLite database file in root directory

### Security Considerations
- **File Upload Security**: Secure filename handling and size restrictions
- **Session Management**: Configurable secret key for session security
- **Database**: Local SQLite storage (suitable for small to medium deployments)
- **Input Validation**: Server-side validation for all user inputs

### Scalability Notes
- **Current Setup**: Single-file Flask application suitable for small teams
- **Database**: SQLite suitable for moderate data volumes
- **File Storage**: Local file system (may need cloud storage for larger deployments)
- **Email**: SMTP-based (may need dedicated email service for high volumes)