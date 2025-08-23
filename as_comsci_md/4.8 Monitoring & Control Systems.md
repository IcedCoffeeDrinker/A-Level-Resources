# 4.8 Monitoring & Control Systems

## Monitoring Systems
- creates a record of a system's condition over a period of time.
- Sensors are used to gather data
  - sensors only output information, the control system is the one to take action
  - a sensor lacks intelligence

## Control Systems
- consist of a monitoring system and one or more actuators connected to controlling devices

**Actuators:** Electrical motors that act upon an electrical signal
- adjusted by controlling devices, e.g. a pane that restricts airflow on a plane wing
- examples: Electric motors, valves, relays

**Controlling Devices:** Take in a control signal from a controller (computer / microprocessor) and turns it into actionable signals for an actuator
- e.g. motor driver, relays
- not PID controllers, etc. as they would decide action

**Controllers:** The brains of the operation which decide what action to take.
- e.g. a computer or microprocessor
- send signals to controlling devices / directly to actuators

**Sensors:** Measure data either continuous or in intervals, output is usually an analogue signal
- often have a build-in analogue to digital converter

## Closed-Loop Feedback Control System

*Diagram Flow Description:*
`Desired value for output` → `Controller` → `Actuator` → `Process` → `actual output`
The `actual output` is fed back to a `Sensor`.
The `Sensor` provides a `measurement` back to the `Controller`.

*Note:*
The $$y'$$ controller also acts as a controlling device here.

## My version:

*Diagram Flow Description:*
1.  **Memory**: Contains `instruction/target value`. Sends a `decision` to the `Controller`.
2.  **Controller**: Receives `decision` from Memory and `Feedback` from the Sensor. Sends an `instruction` to the `Controlling Device`.
3.  **Controlling Device**: (Performs `translation`). Receives `instruction` from the Controller and sends a signal to the `Actuator`.
4.  **Actuator**: Receives the signal from the Controlling Device. Performs an `action` in the physical world. This `actuator action` is also sent to the `Sensor` to be received as feedback.
5.  **Sensor**: Performs a `measurement of the physical world`. Sends `Feedback` to the `Controller`.