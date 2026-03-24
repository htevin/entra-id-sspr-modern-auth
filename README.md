# 🔐 Entra ID: SSPR & Modern Authentication Methods Implementation

## 📌 Project Overview
This lab demonstrates the enterprise-level configuration of Self-Service Password Reset (SSPR) in Microsoft Entra ID utilizing the modern converged Authentication Methods policy. It covers executing a phased, group-based rollout, migrating away from legacy security questions, enforcing user registration policies, and establishing administrative alerting.

By implementing SSPR, organizations drastically reduce Level 1 Helpdesk ticket volumes while simultaneously empowering users to manage their credentials securely and efficiently using modern MFA factors.

## 🛠️ Skills & Technologies Demonstrated
* **Identity Platform:** Microsoft Entra ID
* **Self-Service Password Reset (SSPR):** Configuring SSPR policies and scoping deployments to specific security groups to facilitate phased enterprise rollouts.
* **Modern Authentication Policies:** Migrating away from legacy password reset methods and utilizing the modern converged Authentication Methods policy to enforce secure MFA factors (Email, SMS, Microsoft Authenticator).
* **Compliance & Registration:** Enforcing mandatory SSPR registration upon sign-in and configuring 90-day re-confirmation intervals.
* **Security Auditing:** Enabling automated notification alerts for user and administrator password resets.

## 📖 Business Scenario
"Wayne Enterprises" receives an unsustainable volume of IT Helpdesk tickets solely for password resets. Additionally, the security team mandates migrating away from deprecated, unsecure legacy methods like "Security Questions." As the acting Identity Administrator, the objective is to implement a pilot rollout of SSPR targeted specifically at the "Project Watchtower" task force. The rollout will utilize modern converged authentication policies (Authenticator App, SMS, Email), force users to register upon their next sign-in, and require re-verification every 90 days.

---

## 🚀 Step-by-Step Implementation

### Phase 1: Enable SSPR via Phased Group Rollout
Scoped the SSPR deployment to a specific pilot group rather than applying a blanket tenant-wide policy, adhering to enterprise rollout best practices.

1. Navigated to the [Microsoft Entra admin center](https://entra.microsoft.com) and authenticated using Tenant administrator credentials.
2. From the left navigation menu, expanded the **Protection** section and selected **Password reset**.
3. On the Properties pane, changed the **Self service password reset enabled** setting from "None" to **Selected**.
4. Targeted the deployment by searching for and selecting the **Project Watchtower** pilot group.
   <p>
   <img src="https://imgur.com/Bp3bRnl.png" height="80%" width="80%"/>
   </p>
5. Saved the configuration to apply the policy exclusively to the designated users.

### Phase 2: Migrate to Modern Authentication Policies
Transitioned from legacy SSPR checkboxes (and deprecated Security Questions) to the modern, converged Entra ID Authentication Methods policy to centrally manage MFA and SSPR recovery factors.

1. Navigated to **Protection** > **Authentication methods** > **Policies**.
2. Evaluated the modern list of authentication factors.
3. Enabled **Email** OTP authentication and targeted the pilot user group.
4. Enabled **SMS** and **Microsoft Authenticator** to ensure strong, modern recovery options were available to the task force.
   <p>
   <img src="https://imgur.com/Vmo9VeB.png" height="80%" width="80%"/>
   </p>
5. Confirmed that legacy, unsecure methods (Security Questions) remained disabled in accordance with the upcoming 2027 deprecation.

### Phase 3: Enforce Mandatory Registration Policies
Configured tenant policies to force users to register their recovery information, ensuring the SSPR tool is fully populated and functional before an actual lockout occurs.

1. Navigated back to the **Registration** menu within the SSPR policy.
2. Enforced compliance by setting **Require users to register when signing in?** to **Yes**.
3. Maintained data accuracy by setting **Number of days before users are asked to re-confirm their authentication information** to **90** days.
   <p>
   <img src="https://imgur.com/ce5X0lx.png" height="80%" width="80%"/>
   </p>
4. Saved the configuration.

### Phase 4: Configure Security Alerting
Enabled automated notification alerts to provide visibility into credential changes and mitigate unauthorized administrative access.

1. Navigated to the **Notifications** menu within the SSPR policy.
2. Verified **Notify users on password resets?** was enabled to alert end-users of potential account compromise.
3. Elevated security auditing by setting **Notify all admins when other admins reset their password?** to **Yes**.
   <p>
   <img src="https://imgur.com/u2gSpi0.png" height="80%" width="80%"/>
   </p>
4. Saved the final configuration state.

---
*Disclaimer: This repository is for educational and portfolio demonstration purposes. No actual Kryptonians or Asgardians were harmed during the making of this lab.*
