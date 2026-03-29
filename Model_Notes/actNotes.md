\## \*\*Black-Box Activity Diagram: “Provide Real-Time Weather Data”\*\*



\### \*\*Swimlanes\*\*



1\. \*\*Weather Environment\*\*

2\. \*\*Home Weather Station\*\* (black box)

3\. \*\*Data Storage\*\*

4\. \*\*User Device / User\*\*



\---



\### \*\*Activity Flow\*\*



\*\*Start Node\*\* → \*\*Weather Environment lane\*\*



\* \*\*Generate Sensor Data\*\* → send \*\*Sensor Data\*\* to `Home Weather Station` lane



\*\*Home Weather Station lane\*\*



1\. \*\*Receive Sensor Data\*\*

2\. \*\*Process \& Format Data\*\* (abstract – black-box)

3\. \*\*Decision: Are Alerts Required?\*\*



&#x20;  \* \*\*Yes\*\* → \*\*Send Alert to User Device\*\*

&#x20;  \* \*\*No\*\* → \*\*Send Regular Weather Data to User Device\*\*

4\. \*\*Archive Data in Storage\*\* → send \*\*Archive Data\*\* to `Data Storage` lane



\*\*User Device / User lane\*\* (concurrent/parallel optional)



\* \*\*Receive Weather Data / Alerts\*\* → \*\*Display to User\*\*

\* \*\*User Sends Command\*\* → back to `Home Weather Station` lane



\*\*Home Weather Station lane\*\* (responding to user commands)



\* \*\*Decision: Request Historical / Comparison Data?\*\*



&#x20; \* \*\*Yes\*\* → \*\*Request Data from Storage\*\* → `Data Storage` lane \*\*Retrieve Historical Data\*\* → send \*\*Data Back\*\* → `Home Weather Station` → \*\*Send Data to User Device\*\*



\*\*End Node\*\*



\---



\### \*\*Flow Notes\*\*



\* \*\*All actions inside “Home Weather Station” lane are abstract\*\*; do not show implementation like calculations, database schemas, or WiFi protocols.

\* \*\*Arrows between lanes represent observable flows\*\* only: Sensor Data, Weather Data, Alerts, Archive/Retrieve Data, User Commands.

\* \*\*Decisions\*\* capture system behavior as seen externally: “Are Alerts Required?” or “Request Historical Data?”



\---



\### \*\*Optional Enhancements\*\*



\* Annotate \*\*Measures of Effectiveness\*\* (MoEs) on relevant flows:



&#x20; \* Sensor update frequency

&#x20; \* Maximum WiFi range

&#x20; \* Data retention duration



\* Use \*\*fork/join nodes\*\* if receiving user commands and sensor data concurrently.

