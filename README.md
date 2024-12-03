# Hospital Management System Updated Team 5

## Team Members
- Cole Keim
- Justin Cushing
- James Rogers
- Camden Myers
- Wil Cunningham

## Problem Description
The main objective of this project was to enhance and expand our previous Hospital Management System while showcasing the internal operations of a hospital. The central entity in the new model remains the Patient entity, representing each individual receiving care from the hospital. The hospital's operations continue to be structured around various departments, wards, and staff.

The hospital also maintains records of each patient's financial details through the Billing and Insurance entities. These entities not only facilitate patient care but also ensure accurate documentation to provide better financial coverage. Our goal is to accurately model these relationships, generate representative sample data, and populate the entities accordingly. Additionally, we aim to execute functional queries on this data to derive meaningful business insights into the hospital’s operations.

New features in the system include the addition of a Laboratories branch, which records the details of each patient’s lab tests. The Medical Record entity has been expanded with a new branch, diseases, to document individual diseases for each patient in greater detail and ensure proper organization. The Pharmacy entity has also been introduced, linking directly to billing statements and written prescriptions to ensure smoother workflows and more precise data management.

## Data Model
Our hospital management system is designed to optimize hospital operations and facilitate the efficient delivery of patient care. The model emphasizes the management of staff, patient records, departments, appointments, lab tests, and billing processes.

Patients are at the heart of the system's design. The Patient entity stores key information about individuals receiving care, including their emergency contact details. Each patient is assigned to a Ward, forming a one-to-many relationship since a ward can accommodate multiple patients. Patients may also have multiple Appointments with doctors, represented by a one-to-many relationship between the Patient and Appointment entities. Each appointment record includes details about the attending doctor, as well as the date and time of the consultation. Additionally, each patient can undergo one or more Lab Tests, represented by a one-to-many relationship with the Lab_Tests entity, which records tests performed in a specific laboratory.

Doctors are integral to delivering patient care. The Doctor entity captures essential information about the hospital's medical staff. Each doctor may report to a Senior Doctor, establishing a recursive one-to-many relationship within the Doctor table. Furthermore, each doctor is associated with a specific Department, such as cardiology, surgery, or pediatrics, forming a one-to-many relationship between the Department and Doctor entities. This structure effectively represents the organization of the hospital's medical staff.

Doctors manage appointments with multiple patients, represented by a one-to-many relationship between the Doctor and Appointment entities. During these appointments, doctors may prescribe treatments or medications, which are documented in the Prescription entity. A one-to-many relationship exists between Doctor and Prescription, as a doctor can issue multiple prescriptions, and also between Patient and Prescription, since a patient may receive several prescriptions over time. Each prescription record includes details such as the medication name, dosage, and specific instructions for use. To ensure proper organization, the Pharmacy entity has been added which is represented by a one-to-many relationship with Prescription. This keeps track of which pharmacy each precription was written at, the pharmacy name, location, and the contact number for the pharmacy.

The Nurse entity represents all nurses within the hospital. To reflect the hierarchy, a recursive one-to-many relationship exists within the Nurse table, allowing each nurse to report to a Head Nurse. Additionally, we introduced an associative entity called NurseWardAssignment to manage the assignments of nurses to various wards. This entity models the many-to-many relationship between Nurses and Wards, as a nurse can be assigned to multiple wards, and each ward can have several nurses working in it.

The Ward entity represents various sections within the hospital, such as ICU, Pediatrics, or General Surgery. Each ward is overseen by a Head Nurse, which is captured through a one-to-one relationship between the Ward and Nurse entities for the head nurse role.

The hospital's Medical_Record entity collaborates with the Diseases entity to ensure each patient's information is properly organized and correctly assigned to the patient. A one-to-many relationship exists between Diseases and Medical_Record, as well as between Patient and Medical_Record, since patients may have multiple records for different visits. Each instance of the Diseases entity includes details about the disease, symptoms, duration, severity, and recommended treatment.

In addition to medical care, the hospital management system tracks financial information through the Billing entity. Each Billing record is connected to a Patient and an Insurance provider. The Billing table captures the total amount, the insurance-covered portion, and payment details, ensuring a comprehensive record of the patient's financial obligations. A one-to-one relationship exists between Billing and Insurance, with each billing record linked to a specific insurance policy.

Lastly, the Insurance entity stores information about insurance providers, policies, and coverage periods. This entity helps the hospital manage insurance claims and coverage for patients' medical expenses.

#Data Dictionary

![image](https://github.com/user-attachments/assets/77082899-0cd4-4fa7-b887-50f2ce4e7e11)

Justin image of data table
