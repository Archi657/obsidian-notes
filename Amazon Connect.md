## Concepts

**PSTN** Public Switched Telephone Network (PSTN) is the traditional circuit-switched telephone network for voice calls.
**TFN** are phone numbers with distinct prefix codes that the person initiating the call can dial at no charge.
**DID Numbers** also called Direct Dial-In (DDI) in Europe, are local telephone numbers that match local dialing patterns, managed by single carriers.
**UIFN**  are unique, inbound-only freephone numbers that can be used throughout the world. UIFNs provide toll-free calling across international locations.
Direct Inward Dialing (DID) / Direct Dial Number
**E.164** is a unified global phone number format defined by the International Telecommunication Union (ITU). This format provides international compatibility across telephony systems.
**Call forwarding** is a phone management feature that redirects incoming calls from one telephone number to an alternate number.
**Number porting** Organizations can use number porting to keep their existing phone numbers when migrating their contact center workloads to new carriers.
**SBC** A session border controller (SBC) is a specialized device that protects and controls the flow of IP based communications.
**WebRTC** Web Real-Time Communication (WebRTC) is a project that provides real-time communication capabilities in web browsers and mobile applications. It makes it possible to have peer-to-peer audio, video, and data sharing without the need for proprietary plugins or third-party software installations.
**SRTC** The Secure Real-Time Transport Protocol (SRTP) provides encryption and authentication for real-time multimedia communications, such as VoIP and video over IP networks.
**TLC** TLS is a widely adopted security protocol designed to facilitate privacy and data security for communications over the internet.
**VDI** Virtual desktop infrastructure (VDI) is a virtualization technology that makes it possible for users to access a virtual desktop environment from a remote location.
![[Pasted image 20250807090920.png]]
## Contact Lenses
- Sentiment analysis
- Automated post-contact summaries
- Key highlights
- Sensitive data redaction
- Screen recording
## Quotas
Default values
- Concurrent real-time calls with analytics : 50, but US East 100
- Concurrent post-call analytics job : 200
- Concurrent chat analytics jobs : 200
- Concurrent post-contact summary jobs :10


# Flow
![[Pasted image 20250803215931.png]]

## Flows

### Inbound Flow
These are the primary flows that handle initial customer interactions and are used when a customer initiates a call or chat.
### Campaign Flow
These flows are used to manage what the customer experiences during an outbound campaign.

### Customer queue Flow
These flows are designed to manage customer queues, such as prioritizing certain customers or routing them based on their needs.

### Customer hold Flow
These flows are used to manage what the customer experiences when they are on hold.

With this flow, one or more audio prompts can be played to a customer using the Loop prompts block while they wait on hold.

### Customer whisper Flow
This flow is used to manage what the customer experiences as part of an inbound call immediately before being joined with an agent.

The Agent whisper and Customer whisper flows are played to completion, then the agent and customer are joined.

### Outbound whisper Flow
This flow manages what the customer experiences as part of an outbound call before being connected with an agent.

In this flow, the whisper is played to completion to the customer, then the agent and customer are joined. For example, this flow can be used to enable call recordings for outbound calls with the Set recording and analytics behavior block. For more information, see [Flow Block in Amazon Connect: Set Recording and Analytics Behavior(opens in a new tab)](https://docs.aws.amazon.com/connect/latest/adminguide/set-recording-behavior.html).

### Agent hold Flow
This flow is used to manage what the agent experiences when on hold with a customer.

With this flow, one or more audio prompts can be played to an agent using the Loop prompts block while the customer is on hold.

### Agent whisper Flow
This flow is used to manage what the agent experiences as part of an inbound call immediately before being joined with a customer.

The Agent whisper and Customer whisper flows are played to completion, then the agent and customer are joined.

### Transfer to agent Flow
This flow is used to manage what the agent experiences when transferring to another agent.

This type of flow is used to tranfer a contact directly to an Agent bypassing waiting in a standard queue. For more information, see [Flow Block in Amazon Connect: Transfer to Agent(opens in a new tab)](https://docs.aws.amazon.com/connect/latest/adminguide/transfer-to-agent-block.html).

### Transfer to queue Flow
This flow is used to manage what the agent experiences when transferring to another queue. 

This type of flow transfers contacts to standard queues. A _Set working queue_ block placed earlier in the sequence determines which specific queue receives the incoming contact. This structure ensures proper contact routing and assignment. For more information, see [Flow Block in Amazon Connect: T(opens in a new tab)](https://docs.aws.amazon.com/connect/latest/adminguide/transfer-to-agent-block.html)[ransfer to Queue(opens in a new tab)](https://docs.aws.amazon.com/connect/latest/adminguide/transfer-to-queue.html).

## Flow blocks
https://docs.aws.amazon.com/connect/latest/adminguide/contact-block-definitions.html
### Set logging behavior block 
This block enables flow logs so you can track events as contacts interact with flows. For example, you can use this block to create logs that are sent to Amazon CloudWatch.
### Set recording and analytics behavior block
This block includes settings to enable the following:

- Agent and customer voice recording

- Automated interaction

- Screen recording

- Analytics behaviors for contacts

For example, you can use this block to configure only recording the agent protion of the conversation.
### Set voice block
This block sets the text-to-speech (TTS) language and voice to use for the flow. For example, you can choose any voice available in Amazon Polly.
### Play prompt block
This block plays audio prompts, TTS messages, or chat responses to customers and agents. For example, "Thank you for calling."

### Get customer input block
This block provides tasks, such as capturing customer information, creating interactive phone menus for customer responses, and routing customers to specific paths within a flow. Examples include "Press or say 1 for sales, press or say 2 for support" or "How can I help you today?"

### Check contact atributes block
This block provides branching based on the comparison of the value of a contact attribute to a condition. For example, checking if it's a new or returning caller or if the contact type is a chat contact.

### Set working queue block
This block is used for specifying which queue is going to transfer a contact when the _Transfer to queue_ is invoked. For example, routing a contact to the technical support queue.

### Transfer to queue block
This block transfers the current contact to the queue specified in the Set working queue block. For example, transferring to an agent after collecting information.

### Disconnect
This block ends the contact. For example, after providing information in a self-service scenario.