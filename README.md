---

# Arena Simulation Model: Emergency Department Workflow

## Overview

This simulation model represents the workflow of an emergency department using the Arena simulation software. The model simulates the arrival, treatment, and disposition of patients who come on foot or by ambulance. It tracks various processes, including triage, kiosk processing, treatment in emergency rooms, biochemistry tests, x-rays, and final dispositions such as discharge, transfer, or admission to the hospital.

## Model Components

### 1. **Patient Arrival**
   - **Foot Arrivals:** 
     - Patients arrive at the emergency department on foot with an exponentially distributed inter-arrival time defined by Schedule 1.
   - **Ambulance Arrivals:** 
     - Patients arrive by ambulance with an exponentially distributed inter-arrival time defined by Schedule 2.

### 2. **Triage Process**
   - Patients are assigned a triage level (1, 2, 3, or 4) based on predefined probabilities or conditions.
   - Triage determines the type of treatment the patient will receive, such as being directed to a kiosk or an emergency room.

### 3. **Kiosk Processing**
   - Upon arrival, patients may need to interact with a kiosk. The interaction time is uniformly distributed.

### 4. **Decision Points**
   - The model includes various decision points (BRANCH statements) where patients are routed based on probabilities or conditions:
     - **Triage Decision:** Determines the type of treatment based on triage level.
     - **Post-Treatment Decisions:** After each treatment, patients may be routed to additional tests, treatment, or discharged.

### 5. **Treatment Processes**
   - **Emergency Doctor Rooms:** Patients may be treated in one of several emergency doctor rooms, with processing times following a triangular distribution.
   - **Trauma Room:** Patients needing intensive care are treated in a trauma room, with processing times following a normal distribution.
   - **Biochemistry Test:** Patients may undergo a biochemistry test, with processing times defined by normal or uniform distributions.
   - **X-ray:** Patients may need an x-ray, with processing times following a triangular distribution.

### 6. **Dispositions**
   - After treatment, patients are routed to one of the following outcomes based on probabilities or conditions:
     - **Discharge:** The patient is discharged from the hospital.
     - **Transfer:** The patient is transferred to another facility.
     - **Admission:** The patient is admitted to the hospital.
     - **Deceased:** The patient unfortunately dies and is disposed of from the system.

## Key Metrics

- **NumberIn/NumberOut:** Tracks the number of entities (patients) entering and exiting each process or resource.
- **WIP (Work In Progress):** Monitors the number of patients currently being processed in each resource.
- **Queue Lengths:** Captures the length of queues at various process stages, such as the kiosk, emergency rooms, and biochemistry test.

## Execution

1. **Initialize the Simulation:** Ensure that all schedules, distributions, and resources are correctly defined in the Arena model.
2. **Run the Simulation:** Execute the simulation to observe patient flow, resource utilization, and queue lengths.
3. **Analyze Results:** After the simulation, review key metrics to assess the performance of the emergency department.

## Notes

- The probabilities and distributions used in the model are based on assumptions that should be validated with real data for accurate simulation results.
- Adjustments can be made to schedules, resource capacities, and probabilities to model different scenarios or optimize performance.

## Conclusion

This Arena simulation model provides a framework to study the workflow of an emergency department. It allows for analyzing the impact of patient arrival rates, treatment times, and resource availability on patient outcomes and overall system efficiency.

---
