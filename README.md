# ERAV2-Session-6
## Part 1 
1. Forward Propogation:<br>
- Calculate h1 and h2 - hidden state values for the first hidden layer  <br>
h1 = w1\*i1 + w2*i2  <br> 
h2 = w3\*i1 + w4\*i2  <br>
- Calculate activations a_h1 and a_h2 for h1 and h2 respectively. Here we are using sigmoid as our activation function.  <br>
a_h1 = sigmoid(h1)  <br>
a_h2 = sigmoid(h2)  <br>
- Calculate outputs o1 and o2 using activations from last layer a_h1 and a_h2  <br>
o1 = w5\*a_h1 + w6\*a_h2  <br>
o2 = w7\*a_h1 + w8\*a_h2  <br>
- Calculate activations a_o1 and a_o2 for o1 and o2 respectively using sigmoid.  <br>
a_o1 = sigmoid(o1)  <br> 
a_o2 = sigmoid(o2)<br>
- Calculate error in a_o1 and a_o2 with reference to truth values t1 and t2 respectively.  <br>
E1 = 0.5 * (t1 - a_o1)² <br>
E2 = 0.5 * (t2 - a_o2)²<br>
E_total = E1 + E2<br>
This completes our first forward pass thorugh our nueral network<br>

2. Backward Propogation: <br>
- Calculate partial differential of E_total with reference to each of our weights (parameters), i.e. w1, w2, w3, w5, w6, w7, w8. The derived expressions are listed below:  
∂E_total/∂w5 = (a_01 - t1) * a_o1 * (1 - a_o1) *  a_h1<br>
∂E_total/∂w6 = (a_01 - t1) * a_o1 * (1 - a_o1) *  a_h2<br>
∂E_total/∂w7 = (a_02 - t2) * a_o2 * (1 - a_o2) *  a_h1<br>
∂E_total/∂w8 = (a_02 - t2) * a_o2 * (1 - a_o2) *  a_h2<br> 
∂E_total/∂w1 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w5 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w7) * a_h1 * (1 - a_h1) * i1<br>   												
∂E_total/∂w2 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w5 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w7) * a_h1 * (1 - a_h1) * i2<br>												
∂E_total/∂w3 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w6 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w8) * a_h2 * (1 - a_h2) * i1 <br> 												
∂E_total/∂w4 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w6 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w8) * a_h2 * (1 - a_h2) * i2 <br>

3. Updating weight values using partial derivatives computed as above and learning rate alpha: <br>
w1 = w1 - alpha\*∂E_total/∂w1 <br>
w2 = w2 - alpha\*∂E_total/∂w2 <br>
w3 = w3 - alpha\*∂E_total/∂w3 <br>
w4 = w4 - alpha\*∂E_total/∂w4 <br>
w5 = w5 - alpha\*∂E_total/∂w5 <br>
w6 = w6 - alpha\*∂E_total/∂w6 <br>
w7 = w7 - alpha\*∂E_total/∂w7 <br>
w8 = w8 - alpha\*∂E_total/∂w8 <br>

Repeat above steps until Error saturates. <br>
After completing the excel should look like this <br>
<img width="1300" alt="Screenshot 2024-02-27 at 9 26 14 PM" src="https://github.com/utkarsh2198/ERAV2-Session-6/assets/20721200/21d55cfc-c6c5-425d-b5e7-fb894df523f8">

The error graph when we vary alpha as [0.1, 0.2, 0.5, 0.8, 1.0, 2.0] : <br>

alpha = 0.1 <br>
<img width="500" alt="Screenshot 2024-02-29 at 2 18 45 AM" src="https://github.com/utkarsh2198/ERAV2-Session-6/assets/20721200/fd42f3a5-aab0-4ab9-b57d-42964cd099fd">

alpha = 0.2 <br>
<img width="500" alt="Screenshot 2024-02-29 at 2 19 09 AM" src="https://github.com/utkarsh2198/ERAV2-Session-6/assets/20721200/00ac04cf-157f-44f5-8e84-2a3f8924a505">

alpha = 0.5 <br>
<img width="500" alt="Screenshot 2024-02-29 at 2 19 42 AM" src="https://github.com/utkarsh2198/ERAV2-Session-6/assets/20721200/8673621c-1473-4401-801c-f73820919388">

alpha = 0.8 <br>
<img width="500" alt="Screenshot 2024-02-29 at 2 20 04 AM" src="https://github.com/utkarsh2198/ERAV2-Session-6/assets/20721200/6b13b187-d450-46c9-a4ba-af48ed533ebf">

alpha = 1.0 <br>
<img width="500" alt="Screenshot 2024-02-29 at 2 20 13 AM" src="https://github.com/utkarsh2198/ERAV2-Session-6/assets/20721200/8a42e04d-0090-42d8-8b44-6ce044b8f602">


alpha = 2.0 <br>
<img width="500" alt="Screenshot 2024-02-29 at 2 20 23 AM" src="https://github.com/utkarsh2198/ERAV2-Session-6/assets/20721200/af505fda-7504-4e1b-8e43-bb58b0c0b091">






