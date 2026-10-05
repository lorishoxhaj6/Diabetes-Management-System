# Diabetes Management System (DMS)

A clinical information system for managing and monitoring patients with type 2 diabetes. The software facilitates interaction between **Patient** and **Diabetologist**, enabling continuous tracking of vital parameters, treatment adherence, and symptoms.

## 📄 Official Documentation
For a detailed analysis of the requirements, UML diagrams, and implementation choices, see the:
👉 **[Technical Report (PDF)](RELAZIONE_PROGETTO_INGEGNERIA_DEL_SOFTWARE_.pdf)**

---

## Key Features

The system focuses on proactive monitoring and the prevention of glycemic crises:
* **Glycemic Monitoring**: Daily recording of glucose levels, with an automatic alert system for out-of-range values.
* **Therapy Management**: Diabetologists can prescribe medications and dosages; patients record their intake in real time.
* **Treatment Adherence**: Automatic monitoring of medication intake. If the system detects three consecutive days of missed intake, it generates an alert visible to the physician.
* **Clinical Diary**: Reporting of symptoms, comorbidities, and clinical notes that physicians can update.
* **Traceability**: Built-in logging system that records which physician made changes to the data in real time.

## Architecture and Design Patterns

The project follows an object-oriented design with a clear separation of responsibilities through the following patterns:

### Architectural Patterns
* **Model-View-Controller (MVC)**: Separates application logic (Controller), data structure (Model), and user interface (View).
* **Data Access Object (DAO)**: Isolates the persistence logic (SQL) from the rest of the application. Implemented for entities such as `Patient`, `Measurement`, `Prescription`, `Intake`, and `Symptom`.
* **Facade**:
    * **Clinic Facade**: Unified access point for general clinical functionality.
    * **Alert Service**: Centralized handler for generating and validating clinical alerts.

## 📂 Main Use Cases

### Patient Side
1. **Blood Glucose Logging**: Entering and editing daily measurements before and after meals.
2. **Symptom Reporting**: Selecting predefined symptoms or entering free-text descriptions of comorbidities and concurrent therapies.
3. **Medication Log**: Recording medication intake, specifying date, drug, and dose.

### Diabetologist Side
1. **Therapy Management**: Specifying the drug, dosage, and instructions for assigned patients.
2. **Data Viewing**: Monitoring glycemic trends, reported symptoms, and medications taken by the patient.
3. **Record Updates**: Adding updated clinical notes or reports.

## 🛠️ Development and Quality

* **Methodology**: Agile, incremental approach using **Pair Designing** and **Pair Programming**.
* **Automated Testing**: **JUnit** is used to validate the persistence layer (`JdbcPatientDao` and `JdbcMeasurementDao`).
* **User Validation**: Usability tests conducted with non-expert users to verify the interface is intuitive.

---
**Developers**: [Loris Hoxhaj, Andrew Bregoli, Lorenzo Oceano]
*Project developed for the Software Engineering course*
