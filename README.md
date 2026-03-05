# USB Medical System - iDempiere Plugin (`org.consultorio.usb`)

A custom OSGi plugin developed for the iDempiere ERP system to manage medical appointments, patient records, and automated billing.

## 🚀 Features

* **Patient Management:** Register and manage patient data (Name, TaxID) mapping directly to iDempiere's `C_BPartner`.
* **Appointment Scheduling:** Create medical appointments linking patients, doctors, and medical services (`M_Product`).
* **Automated Billing:** Custom `SvrProcess` (`GenerarFacturaCita`) that automatically generates an AR Invoice (`C_Invoice`) from a scheduled appointment.
* **Smart Automation:** Includes a Callout (`CalloutCita`) to auto-complete service prices and a Model Validator (`CitaValidator`) to prevent overlapping appointments for the same doctor.
* **Reporting:** Generates a printable Appointment Sheet (Hoja de Cita) in PDF format using JasperReports.

## 🛠️ Tech Stack & Architecture

* **ERP Framework:** iDempiere Core
* **Architecture:** OSGi Plugin with `Active Record` pattern for custom tables (`MED_PACIENTE`, `MED_CITA`).
* **Database:** PostgreSQL
* **Java Version:** Amazon Corretto 17
* **Build Tool:** Maven

## 📋 Prerequisites

Before setting up this plugin, ensure you have the following installed:
* Amazon Corretto 17 configured as your primary JDK.
* Maven installed for dependency resolution.
* A running instance of PostgreSQL with the official iDempiere seed database imported.

## 💻 Development Setup (Eclipse)

1. Clone this repository and import it into Eclipse as a **Plug-in Project**.
2. Configure your iDempiere **Target Platform**.
3. Run the project using the `server.product` configuration.

## 📦 Production Deployment

1. In Eclipse, right-click the project and select **Export → Deployable plug-ins and fragments**.
2. Copy the generated `.jar` file to your server's `{iDempiere}/plugins/` directory.
3. Restart the iDempiere server.
4. Execute the necessary SQL metadata scripts via the Application Dictionary.

## 👨‍💻 Author
**John Garrido**
