This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules. The application interacts with two databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which in turn delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document models.

1. User accesses AdminDashboard, DoctorDashboard, PatientDashboard, PatientRecord or Appointment pages.
2. The action is routed to the appropriate Thymeleaf or REST controller.
3. The controller calls the service layer.
4. Service layer communicates with repository layer. This layer applies business rules and validations, ensures a clean separation between controller logic and data access 
5. Repository layer performs data access operations. This layer will include MySQL and MongoDB repositries. MySQL uses Spring Data JPA to manage structured ralational data like patients, doctors, appointments and admin records while MongoDB manages document based records like prescriptions.
6. Database Access are performed by database engines. MySQL stores core entities users, roles, appointments along with all constraints. While MongoDB stores flexible data structure for prescriptions.
7. Once data is retrieved from database access layer it is mapped to the Java model classes that is used by application layer.
8. The models are serialized into JSON and sent back to the client as a response in REST controllers. In MVC flows models are passed from controllers to templates where these are rendered as HTML in browser. 
...