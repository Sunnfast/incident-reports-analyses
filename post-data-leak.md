# title
A set of recommendations for security hardening practices to be implemented in an organization in response to recent data leak. This analysis was part of the coursework for the Google Cybersecurity Professional Certificate.

### Incident Summary [excerpt]
A sales manager shared access to a folder of internal-only documents with their team during a meeting. The folder contained files associated with a new product that has not been publicly announced. It also included customer analytics and promotional materials. After the meeting, the manager did not revoke access to the internal folder, but warned the team to wait for approval before sharing the promotional materials with others.

During a video call with a business partner, a member of the sales team forgot the warning from their manager. The sales representative intended to share a link to the promotional materials so that the business partner could circulate the materials to their customers. However, the sales representative accidentally shared a link to the internal folder instead. Later, the business partner posted the link on their company's social media page assuming that it was the promotional materials.

### Issues
1. Access to an internal folder with sensitive information was not properly limited to the sales team and their manager.
2. A business partner should not have been given approval to share the information on social media.

### Review - NIST SP 800-53: AC-6
NIST SP 800: AC-6: Least Privilege
* Control Statement: Employ the principle of least privilege, allowing only authorized accesses for users (or processes acting on behalf of users) that are necessary to accomplish assigned organizational tasks.


**Applicability:** NIST SP 800: AC-6 addresses how an organization can protect its data through the principle of least privilege included are also control enhancements to improve the efficacy of least privilege.

### Recommendations
* Restrict access to sensitive resources based on user role (i.e. implement some form of RBAC). (NIST SP 800: AC-6(7))
* Regularly audit user privileges to ensure privilege creep is not occurring. (NIST SP 800: AC-6(9))


### Justification
This issue was caused by an internal file being shared with an external business partner. Restricting sensitive internal information so that outsiders cannot access it will aid in preventing future data leaks. Additionally, a requirement where the security team to routinely audit access and permissions to files would help decrease the chances of future information being exposed.
