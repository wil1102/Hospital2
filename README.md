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

![image](https://github.com/user-attachments/assets/70e782e5-5ba9-4582-b6e0-8b90d30e6424)
![image](https://github.com/user-attachments/assets/48042ac0-eb53-4642-9528-30efe598082d)
![image](https://github.com/user-attachments/assets/3b414ac8-28c1-47b6-a326-0280653a2753)
![image](https://github.com/user-attachments/assets/661972d7-e242-41a3-90df-f1c3f408b0dd)
![image](https://github.com/user-attachments/assets/35a6efea-1f4b-4bed-9507-636ce7d7b7cb)

## Queries

Query 1: 
Query: Return the senior doctor(s) with the highest amount of subordinate doctors
Why? Track which senior doctors carry the heaviest workload in the supervision of subordinate doctors
![image](https://github.com/user-attachments/assets/7990fce9-28c4-47a8-a190-fe4734712a5a)

Query 2:
Query: Show how many appointments each doctor had per year
Why?: Useful for performance reports
![image](https://github.com/user-attachments/assets/2e274af7-6078-43bf-aede-fbaa87e20903)

Query 3:
Query: View with limited patient and billing info
Why?: this allows the finanace teams to work on data involving how much money they are still expecting to recieve without having access to sensitive personal patient information like their name and SSN
![image](https://github.com/user-attachments/assets/1e2b583d-d751-4b2b-a6cb-aaa82cd09183)
![image](https://github.com/user-attachments/assets/b5b2bdf2-1bcc-4f00-b2f1-a2dfd5f6a33b)
![image](https://github.com/user-attachments/assets/206d729e-c2c4-460c-9aa8-ce8a81ac36f7)
![image](https://github.com/user-attachments/assets/69bf8889-fbcf-4c2d-a649-c86080845749)
![image](https://github.com/user-attachments/assets/b9ae6e2d-3276-458d-87e5-0a4a76a94938)

Query 4:
Query: shows financial and appointment info for any given doctor after inputting first and last name
Why?: useful to check which doctors are or are not meeting financial quotas
![image](https://github.com/user-attachments/assets/ca737d96-e58c-4afe-a40a-599e72aa966d)
![image](https://github.com/user-attachments/assets/2582bb8f-827f-4a0d-a2f4-b9f3b69cf241)
![image](https://github.com/user-attachments/assets/ead0ac73-6eb2-406d-bcf0-4583a8be39a3)
![image](https://github.com/user-attachments/assets/e7b12897-bff9-44fb-a7e9-57fab19fc546)





