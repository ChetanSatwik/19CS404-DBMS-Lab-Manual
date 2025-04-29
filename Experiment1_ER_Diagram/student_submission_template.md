# ER Diagram Submission - Student Name

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
![ER Diagram](er_diagram.png)
![WhatsApp Image 2025-04-29 at 23 13 04_592e0efd](https://github.com/user-attachments/assets/f4b576e0-5349-44ca-b2d7-f0d573c04ad4)



## Entities and Attributes:
- DOCTOR : DoctorID,Name,Specialization,Phone.
- DEPARTMENT : DeptID,DeptHead,DeptName.
- PATIENT : PatientID,DOB,Phone,Address,Gender,Name.
- APPOINTMENT : AppointmentID,DoctorID,Reason,Date and Time.
- MEDICAL COVER : RecordID,PatientID,DoctorID,Diagnosis,Prescribed medicine.

## Relationships and Constraints:
- Assigned to (Doctor–Department):
- Cardinality: Many Doctors → One Department
- Participation: Total (Doctor), Partial (Department)
- Conducts (Doctor–Appointment):
- Cardinality: One Doctor → Many Appointments
- Participation: Partial (Doctor), Total (Appointment)
- Schedule (Patient–Appointment):
- Cardinality: One Patient → Many Appointments
- Participation: Total (Patient), Total (Appointment)
- Has records (Appointment–Medical cover):
- Cardinality: One Appointment → One Medical cover
- Participation: Partial (Appointment), Total (Medical cover)

## Extension (Prerequisite / Billing):
Extension: Billing
 New Entity: Billing
 Attributes:
 Billing id
 Appointment id (FK)
 Patient id (FK)
 Amount
 Payment status
 Payment method
 Billing date
 New Relationship:
 Billed for (Appointment–Billing):
 Cardinality: One Appointment → One Billing
 Participation: Partial (Appointment), Total (Billing)
Why This Works: Billing is logically tied to an appointment.
 It references the patient who is billed and can track whether payment is complete, partially paid, or
 pending.

## Design Choices:
Brief explanation of why you chose certain entities, relationships, and assumptions.
Design Choices Entities:
 Doctor, Patient, Department, Appointment, Medical Cover
 These were chosen as entities because they represent core, real-world objects with multiple
 attributes and independent existence within a healthcare domain.
 Doctor and Patient are obvious primary actors.
 Department organizes doctors and provides structure.
 Appointment is a central event where interaction occurs between doctors and patients.
 Medical Cover (essentially medical records) captures diagnosis and prescriptions linked to
 appointments.
 Relationships:
 Assigned to (Doctor–Department):
 Doctors work in departments, and this relationship ensures organizational hierarchy.
 Conducts (Doctor–Appointment):
 Doctors conduct appointments. This shows the service aspect of their role.
 Schedule (Patient–Appointment):
 Patients initiate the interaction by scheduling appointments.
 Has Records (Appointment–Medical Cover):
 Every appointment may result in medical documentation. Capturing this ensures accurate
 tracking of treatment history.
 Assumptions:
 Each appointment is with one doctor and one patient.
 A medical record is tied directly to an appointment, not existing independently.
 Doctors can belong to only one department, simplifying organizational structure.
 Patients can have multiple appointments, and likewise, a doctor can conduct many
 appointments.
 No billing or insurance is shown, so assumed out of scope unless extended later.
