# Software Requirement Readiness Levels (ScRL)

## Flows
### Key Flow(s)
* Main critical flow(s) of the system
* **Example:**
    
    select products → add to a cart → check out a cart → select a payment method → pay → get confirm msg → done
    
### Alternative Flows
#### Regular Variance
* Alternative detours which can happen mid-key-flow(s)
* **Example:**

    **Trying to buy products without logging in**

    select products → add to a cart → **login** → check out a cart → select a payment method → pay → get a confirm message

#### Exceptional Flow
* Various kinds of failures mid-key-flow(s)

## Levels
1. **Concept & Principle**
    * Identify Key Flows
2. **Requirement & Architecture**
3. **Detailed Design**
    * Diagrams

    ======= **Design is Ready for Development** =======

4. **Verification (Laboratory)**
    * Key flows are unit-tested
    * Key flows are integration-tested in dev
5. **Verification (Relevant)**
    * Same as above but in a testing environment
6. **Verification (End-to-End)**
    * Same as above but in a pre-production environment with real cases, data, and external systems
    
    ======= **Key Flows are Ready for Demonstration to Stakeholders** =======
7. **Demo (High-Fidelity)**
    * **ALL** flows are tested like in **6.**

    ======= **The Requirement is Ready for Pilot Users** =======

8. **Mission Qualified**
    * **ALL** flows are non-functional-tested in pre-production
    * Standards-checking (if any)
9.  **Mission Proven**
    
    ======= **The Requirement is Ready for Delivery to Customers** =======

## Priority of Requirements
* Critical (Required)
  * Reqs with high-value to the goal
  * **Example:**
    * Adding Items to Cart
    * Checking-out a Shopping Cart
    * Posting new products
* Standard (Mandatory)
  * Reqs which support the critical reqs
  * **Example:**
    * Sign Up
    * Login
    * Forgot Password
* Optional (Nice to Have)
  * Reqs which have low impact to the goal
  * **Example:**
    * User Profile
    * About Us Page
    * Minigames