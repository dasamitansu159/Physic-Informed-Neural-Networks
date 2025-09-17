# Physic-Informed-Neural-Networks
This contains all the code of the problems that we have presented in the report 
# Physics-Informed Neural Networks (PINNs)

This repository contains implementations of **Physics-Informed Neural Networks (PINNs)** for solving classical partial differential equations (PDEs).  
PINNs integrate deep learning with physics constraints, ensuring that solutions satisfy governing laws like conservation of mass, momentum, and energy.

This work was completed during my **Summer Internship 2024 at IIT Delhi**.

---

## 🔥 Problems Solved & Results

### 1. Heat Equation (1D)

**Equation:**
\[
\frac{\partial u}{\partial t} = \alpha^2 \frac{\partial^2 u}{\partial x^2}, \quad \alpha = 2
\]

**Domain:** \(0 \leq x \leq 2,\; 0 \leq t \leq 0.2\)  

**Initial Condition:**  
\[
u(x,0) = x^2(2-x)
\]

**Boundary Conditions:**  
\[
u(0,t) = 0, \quad u(2,t) = 0
\]

**Result:**  
![Heat 1D](results/heat1d.png)

---

### 2. Heat Equation (2D)

**Equation:**
\[
\frac{\partial u}{\partial t} = \alpha^2 \left( \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} \right), \quad \alpha = 0.1
\]

**Domain:** \(0 \leq x,y \leq 1,\; 0 \leq t \leq 1\)  

**Initial Condition:**  
\[
u(x,y,0) = \sin(\pi x)\sin(\pi y)
\]

**Boundary Conditions:**  
\[
u(x,0,t) = u(x,1,t) = u(0,y,t) = u(1,y,t) = 0
\]

**Result:**  
![Heat 2D](results/heat2d.png)

---

### 3. Advection Equation (2D)

**Equation:**
\[
\frac{\partial u}{\partial t} + c_x \frac{\partial u}{\partial x} + c_y \frac{\partial u}{\partial y} = 0, 
\quad c_x = 1,\; c_y = 1
\]

**Domain:** \(0 \leq x,y \leq 1,\; 0 \leq t \leq 1\)  

**Initial Condition:**  
\[
u(x,y,0) = \sin(\pi x)\sin(\pi y)
\]

**Boundary Conditions:** Periodic  
\[
u(0,y,t) = u(1,y,t), \quad u(x,0,t) = u(x,1,t)
\]

**Result:**  
![Advection](results/advection.png)

---

### 4. Schrödinger Equation

**Equation:**
\[
i \frac{\partial h}{\partial t} + \frac{1}{2}\frac{\partial^2 h}{\partial x^2} + |h|^2 h = 0
\]

**Domain:** \(-5 \leq x \leq 5,\; 0 \leq t \leq \pi/2\)  

**Initial Condition:**  
\[
h(0,x) = 2\,\text{sech}(x)
\]

**Boundary Conditions:** Periodic  
\[
h(t,-5) = h(t,5), \quad \frac{\partial h}{\partial x}(t,-5) = \frac{\partial h}{\partial x}(t,5)
\]

**Result:**  
![Schrödinger](results/schrodinger.png)

---

### 5. Burgers’ Equation

**Equation:**
\[
\frac{\partial u}{\partial t} + u\frac{\partial u}{\partial x} - \nu \frac{\partial^2 u}{\partial x^2} = 0, 
\quad \nu = \frac{0.01}{\pi}
\]

**Domain:** \(-1 \leq x \leq 1,\; 0 \leq t \leq 2\)  

**Initial Condition:**  
\[
u(0,x) = -\sin(\pi x)
\]

**Boundary Conditions:**  
\[
u(t,-1) = u(t,1) = 0
\]

**Result:**  
![Burgers](results/burgers.png)

---

### 6. Allen–Cahn Equation

**Equation:**
\[
\frac{\partial u}{\partial t} = \nu \frac{\partial^2 u}{\partial x^2} + 5u - 5u^3, \quad \nu = 10^{-4}
\]

**Domain:** \(-1 \leq x \leq 1,\; 0 \leq t \leq 1\)  

**Initial Condition:**  
\[
u(x,0) = \cos(\pi x)
\]

**Boundary Conditions:**  
\[
u(-1,t) = u(1,t)
\]

**Result:**  
![Allen-Cahn](results/allen_cahn.png)

---

### 7. Lid-Driven Cavity Flow (Navier–Stokes, Re=100)

**Equations:**
\[
u\frac{\partial u}{\partial x} + v\frac{\partial u}{\partial y} + \frac{1}{\rho}\frac{\partial p}{\partial x} - \nu \left( \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} \right) = 0
\]

\[
u\frac{\partial v}{\partial x} + v\frac{\partial v}{\partial y} + \frac{1}{\rho}\frac{\partial p}{\partial y} - \nu \left( \frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2} \right) = 0
\]

\[
\frac{\partial u}{\partial x} + \frac{\partial v}{\partial y} = 0
\]

**Domain:** \(0 \leq x,y \leq 1\)  

**Boundary Conditions:**  
- Top lid (y=1): \(u=U,\; v=0\)  
- Other walls: \(u=v=0\)

**Result:**  
![Lid Driven Cavity](results/ldc.png)

---

### 8. Thin Film Dewetting

**Equation:**
\[
H_T + \left( \frac{H^3}{H_0^3} (H_{XXX} + \Phi H_X) \right)_X = 0
\]

**Domain:** \(x \in [0,\lambda], \; t \in [0,1.5]\)  

**Initial Condition:**  
\[
H(x,0) = 1 + 0.001 \cos\left(\frac{2\pi x}{L}\right)
\]

**Boundary Condition:** Periodic  
\[
H(0,t) = H(L,t)
\]

**Result:**  
![Thin Film](results/thinfilm.png)

---

## 🛠 Tech Stack
- Python  
- TensorFlow / PyTorch / JAX  
- Matplotlib for visualization  

---

## 📚 References
- Raissi, M., Perdikaris, P., & Karniadakis, G. E. (2019). *Physics-Informed Neural Networks: A Deep Learning Framework for Solving Forward and Inverse Problems Involving Nonlinear PDEs*. Journal of Computational Physics, 378, 686–707.  
- Additional references included in my [Internship Report](./Internship_Report.pdf).  

---

## ✍️ Author
**Amitansu Das**  
B.Tech, Chemical Engineering, NIT Warangal  
Summer Intern 2024 @ IIT Delhi  

---
