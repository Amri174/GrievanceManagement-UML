# GrievanceManagement-UML
Developed UML models for a citizen services portal, designed using IBM Rational Software. This contains functionalities like grievance registration, online payments and service requests.

## System Overview
The diagrams describes a citizen-centric system that offers various online services like online payment, tax payment, viewing payment histories, printing challans, requesting new services, registering grievances and tracking the request status. It involves interactions between citizens and a central system, with specific modules and processes for handling these diverse functions.

## Object-Oriented Analysis (OOA) Diagrams
Object-Oriented Analysis (OOA) is a crucial phase in software development. It focuses on understanding and defining system requirements by identifying objects, their attributes, behaviors, and interactions. OOA helps in creating a model of the system's problem domain. The UML diagrams provided illustrate key aspects of an OOA for a citizen-centric online services system.

The primary techniques in OOA often include:
*   **Object Modeling:** Defines the static structure of the system (e.g., classes and their relationships).
*   **Dynamic Modeling:** Describes the system's behavior over time and in response to events.
*   **Functional Modeling:** Details the processes and data transformations within the system [8].

The following diagrams are central to this system's OOA:

## UML Diagrams
The system's architecture and functionality are detailed through the following UML diagrams:

### Class Diagram
This diagram presents a static structural view of the system, detailing key software classes, their attributes, methods, and the relationships between them.

<img src="Assets/Class%20Diagram.PNG" alt="Use Case Diagram" width=500px height=400px >

###

<details>
<summary><b>Key Classes Description(Click to expand)</b></summary>
<br>
  
*   **`Citizen`**: Represents a user interacting with the system.
    *   Attributes: `name: String`, `address: String`
    *   Methods: `login()`, `logout()`
    *   This class has a connection (`+connectsTo`) with the `Syst` class.
*   **`Syst` (System)**: Appears to be a central coordinating class.
    *   Attributes: `IPAdd: Integer`
    *   Methods: `ReqService()`, `TrackStatus()`
*   **`SecureOnlinePayment`**: Manages the process of secure online payments.
    *   Attributes: `UserID: Integer`, `PayID: Integer`
    *   Methods: `pay()`
    *   It establishes a payment connection (`+establishPaymentConnection`) with `Syst`.
*   **`PayTax`**: Handles functionalities related to tax payments.
    *   Attributes: `propertytype: Integer`, `waterconsumption: Integer`, `Income: Integer`
    *   Methods: `payonline()`, `cancelpayment()`
    *   It interacts with `Syst` to get tax-related information (`+GetTax`).
*   **`ViewPaymentHistory`**: Responsible for displaying a user's payment history.
    *   Methods: `display()`
    *   It is associated with `Syst`, likely to retrieve data.
*   **`PrintChallan`**: Manages the generation and retrieval of challans.
    *   Methods: `generateE-challan()`, `GetChallan()`
    *   It interacts with `Syst` to obtain challan data.
</details>

### 

**Relationships:**
The `Syst` class is central, with `Citizen`, `SecureOnlinePayment`, `PayTax`, `ViewPaymentHistory`, and `PrintChallan` all having direct associations with it. `Syst` manages major core services.
   
### 

   
### Use Case Diagram
This diagram shows the primary interactions between users (actors) and the system, displaying all main services.
<img src="Assets/Use%20Case%20Diagram.PNG" alt="Use Case Diagram" width=500px height=400px>

###

<details>
<summary><b>Actors and Key Use Cases Description(Click to expand)</b></summary>
<br>

**Actors:**
*   **Citizen:** End-user who initiates service requests and interacts with the system's features.
*   **Systm (System):** Represents the core backend system that processes requests, manages data, and facilitates services.
*   **Payment:** An actor involved in payment-related use cases. It consists either external payment gateway or a specialized internal payment handling module.

**Key Use Cases (primarily initiated by the Citizen):**
*   **Secure OnlinePayment:** Enables User to conduct financial transactions securely. This involves the Citizen, Payment, and Systm actors.
*   **View PaymentHistory:** Allows citizens to access records of their past payments. This involves the Citizen, Payment, and Systm actors.
*   **Print Challan:** Provides functionality for citizens to generate and print payment challans. This involves the Citizen, Payment, and Systm actors.
*   **Pay Tax:** Facilitates the online payment of taxes by citizens. This involves the Citizen, Payment, and Systm actors.
*   **Request NewService:** Allows citizens to apply for new services provided by the system. This involves the Citizen and Systm actors.
*   **Register Grievance:** Enables citizens to submit complaints or grievances. This involves the Citizen and Systm actors.
*   **Track OnlineStatus:** Allows citizens to monitor the progress or status of their submitted requests or applications. This involves the Citizen and Systm actors.

</details>

### 

### Activity Diagram: Grievance Submission
This diagram illustrates the sequential flow of actions involved with the "Register Grievance" process.
<img src="Assets/Activity%20Diagram.PNG" alt="Activity Diagram" width="300" height="400">

<details>
<summary><b>Process Description (Click to expand)</b></summary>
<br>
  
**Process Steps:**
1.  The process begins with the user action: **Enter Username & Password**.
2.  A decision point follows: **Validate**.
    *   If credentials are not valid, the flow loops back to "Enter Username & Password".
    *   If credentials are valid, the flow proceeds.
3.  The user then performs the action: **Select Grievance**, choosing the nature of their issue.
4.  Next, the user proceeds to **Enter Grievance**, providing the specific details.
5.  The user then chooses to **Submit Grievance**.
6.  The process concludes with the system action: **Display "Submitted"**, confirming receipt of the grievance.
</details>


### Relevant Repositories
Here are some of my other projects that are similar:

*   [**UML-Class-Diagram**](https://github.com/Amri174/UML-Class-Diagram)
*   [**UML-Sequence-Diagram**](https://github.com/Amri174/UML-Sequence-Diagram)
*   [**UML-Usecase-Diagram**](https://github.com/Amri174/UML-Usecase-Diagram)

###



