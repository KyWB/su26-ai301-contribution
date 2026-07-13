[contribution_readme.md](https://github.com/user-attachments/files/28405999/contribution_readme.md)
# su26-ai301-contribution# Contribution [#]: [Issue Title]

**Contribution Number:** [2]  
**Student:** [Kyron Castellanos]  
**Issue:** [https://github.com/home-assistant/android/issues/5341]

**Status:** Status: Phase I Complete

---

## Why I Chose This Issue

I chose issue #5341 on the Home Assistant Android repository because it provides a practical opportunity to work on a widely used, open-source IoT platform. Developing for an application that manages local network routing and device states bridges the gap between client-side software engineering and infrastructure management.

I am interested in this because:

Working on Home Assistant aligns perfectly with my current preparation for the CCNA certification, as the platform heavily relies on understanding how devices communicate and resolve across local networks.

It allows me to apply my software development background—particularly my experience building complex logic in C++ and Python—to a large-scale mobile ecosystem.

Troubleshooting application behavior in a networked environment serves as excellent hands-on practice for my long-term goals in penetration testing and red-teaming, where understanding endpoint behaviors and traffic flow is critical.

Contributing to a major, active repository directly supports my objectives for the AI301 Open Source Capstone.

From reading the issue description and thread, the problem is that certain user interfaces within the client (such as adding a moderator to an open group) fail to parse an ONS name, treating it as an invalid public key format instead of resolving it. My contribution will update the client's input handling behavior to cleanly intercept inputs, check for ONS strings, resolve them to their corresponding public keys, and seamlessly pass that data forward.

I have commented on the issue thread to formally register my interest in implementing this component.

---

## Understanding the Issue

### Problem Description

The data models AssistPipelineRunStart and AssistPipelineSttEnd currently utilize a loose Map<String, Any?> structure to hold their event payloads. This forces the application to accept arbitrary data types and requires downstream components to perform manual, runtime type-casting whenever they need to read specific fields.

### Expected Behavior

Event payloads for the Assist Pipeline should be explicitly mapped using strongly-typed Kotlin data classes. The application should declare properties matching the exact fields expected from the Home Assistant core server, ensuring compile-time type safety and removing arbitrary Any? casting.

### Current Behavior

The codebase uses generic key-value maps (Map<String, Any?>) for pipeline start and Speech-to-Text (STT) end events. This makes the code harder to maintain, hides the contract between the server and the app, and risks runtime crashes if a value is incorrectly cast.

### Affected Components

data/src/main/java/.../websocket/entities/ (Likely location of the Assist Pipeline data models)

domain/src/main/java/.../ (Classes handling the serialization/deserialization logic for Assist WebSocket events)

Any UI components or background services consuming these specific pipeline lifecycle triggers.

---

## Reproduction Process

### Environment Setup


### Steps to Reproduce


### Reproduction Evidence



---

## Solution Approach

### Analysis



### Proposed Solution


### Implementation Plan


---

## Testing Strategy

  
### Unit Tests


### Integration Tests


### Manual Testing


---

## Implementation Notes

Week 3 Progress



### Week 4 Progress


### Code Changes

- **Files modified:**


---

## Pull Request

**PR Link:**

**PR Description:** 


**Maintainer Feedback:**


**Status:** 

---

## Learnings & Reflections

### Technical Skills Gained



### Challenges Overcome



### What I'd Do Differently Next Time


---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
