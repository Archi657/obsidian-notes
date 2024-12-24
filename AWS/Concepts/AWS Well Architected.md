[Amazon Well Architected Site](https://aws.amazon.com/architecture/well-architected/?nc1=h_ls&wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc&wa-guidance-whitepapers.sort-by=item.additionalFields.sortDate&wa-guidance-whitepapers.sort-order=desc)
Six Pillars
1. **Operational Excellence**
   The operational excellence pillar focuses on running and monitoring systems, and continually improving processes and procedures. Key topics include automating changes, responding to events, and defining standards to manage daily operations.
2. **Security**
   The security pillar focuses on protecting information and systems. Key topics include confidentiality and integrity of data, managing user permissions, and establishing controls to detect security events.
3. **Reliability**
   The reliability pillar focuses on workloads performing their intended functions and how to recover quickly from failure to meet demands. Key topics include distributed system design, recovery planning, and adapting to changing requirements.
4. **Performance Efficiency**
   The performance efficiency pillar focuses on structured and streamlined allocation of IT and computing resources. Key topics include selecting resource types and sizes optimized for workload requirements, monitoring performance, and maintaining efficiency as business needs evolve.
5. **Cost Optimization**
   The cost optimization pillar focuses on avoiding unnecessary costs. Key topics include understanding spending over time and controlling fund allocation, selecting resources of the right type and quantity, and scaling to meet business needs without overspending.
6. **Sustainability**
   The sustainability pillar focuses on minimizing the environmental impacts of running cloud workloads. Key topics include a shared responsibility model for sustainability, understanding impact, and maximizing utilization to minimize required resources and reduce downstream impacts.
---

To build secure, high-performing, resilient, and efficient infrastructure.
- AWS Well-Architected Tool **NO COST** in the AWS Management Console.

Roles mentioned in Sustainability doc : chief technology officers (CTOs), architects, developers, and operations team members.

---

Loose coupling: This is a design principle that promotes independence between components in a system. It enhances flexibility and scalability by reducing dependencies. While beneficial for system architecture, it doesn't directly target cost optimization. 

Rightsizing: Involves selecting the appropriate size and type of AWS resources to match the workload's actual needs. The focus is on optimizing costs by avoiding overprovisioning and ensuring resources are efficiently utilized. Regular reviews and adjustments contribute to ongoing cost-effectiveness. 

Caching: Involves storing frequently accessed data to reduce the need to fetch it repeatedly from the original source. It improves performance and can indirectly contribute to cost savings by reducing the load on backend resources. The primary focus, however, is on enhancing application performance rather than direct cost optimization. 

Redundancy: Involves having duplicate components to ensure high availability and fault tolerance. While crucial for reliability and minimizing downtime, redundancy's primary goal is not direct cost optimization. It can prevent costs associated with disruptions and