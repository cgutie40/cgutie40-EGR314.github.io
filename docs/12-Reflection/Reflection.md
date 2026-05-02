## Review of Module's Success
Most product requirements were successfully met, with a few partially achieved or missed. TR-01 was partially met, as wireless commands from the HMI worked, but the wheel subsystem caused the rover to lock after a single input. TR-02, TR-03, TR-04, and TR-05 were fully met, with the rover operating on battery power and successfully capturing humidity and temperature data while being controlled through the HMI.

Communication requirements were largely successful. TR-06 and TR-07 were met, with reliable bidirectional data transfer, though some latency occurred under poor WiFi conditions. TR-09 was also fully satisfied, with successful transmission of system status and errors. TR-08 was not met due to the pressure subsystem not being implemented, and TR-10 was only partially met, as startup exceeded the desired 10-second target.

Overall, the system met most core requirements and demonstrated successful integration, with remaining issues primarily related to specific subsystems and performance targets.

## Microcontroller/Module Startup Tip
For the Wireless Communication Subsystem, choosing the ESP32 was a strong decision due to its built-in WiFi capabilities and overall flexibility. While MQTT over WiFi worked well, Bluetooth could have been an alternative approach. However, implementing a reliable Bluetooth communication protocol would have required significantly more development time and coordination with the rover’s local communication subsystem. Although Bluetooth may have reduced latency and provided a more stable connection for the HMI, the added complexity made WiFi a more practical choice within project constraints.

One key takeaway is the importance of understanding the full capabilities of the ESP32. Reviewing the datasheet and becoming familiar with its pins and peripherals helped guide design decisions and ensured that only necessary features were included, resulting in a more reliable subsystem. Additionally, having prior exposure to Bluetooth implementation, such as through a structured lab or provided resources, would have made it easier to confidently consider it for the final design.

## Lessons Learned

1. Team coordination is critical. Meeting weekly and staying on top of assigned tasks helped keep the project on track.
2. For individual subsystems, it is important to thoroughly research your components and understand how they integrate into the overall system design.
3. Class labs often include components and concepts that are directly applicable to the project. Paying attention and saving that work can be very useful later.
4. Practicing and researching techniques to improve soldering skills is essential, especially when working with small surface-mount components.
5. Communication is key. If issues arise, it is important to talk with your team and seek help from TAs or the professor when needed.
6. When selecting components, always double-check the recommended circuit design in the datasheet and ensure you include all required supporting components.
7. When ordering parts, coordinate with your team. Using the same component sizes allows for sharing parts if needed, saving both time and cost.
8. Start PCB design early and take your time. Carefully consider layout decisions and allow sufficient space for each major subsystem component.
9. Review your designs with teammates and even other groups, not just the TA or professor, to catch potential issues early.
10. Document everything throughout the project. Keeping organized records will make it much easier to complete the final report.

## Recommendations for Future Students

1. Be thoughtful when choosing your team and teammates. A larger team does not necessarily mean less work, as it can introduce more complexity and require stronger organization; aim for a team that works well together and is interdependent.
2. Make an effort to be present in class and team meetings. Even if your role is not immediately critical, your participation contributes to the overall success of the team.
3. Invest time in conducting research outside of class and share your findings with your team to strengthen the overall project.
4. Support your teammates whenever possible. Many students have different skills and knowledge, and taking initiative to help others can improve both team performance and project outcomes.
5. Accept that you will not understand everything right away. The purpose of the class is to learn, so prioritize asking questions and seeking clarification through research or guidance when needed.
