# Quantum Key Distribution - BB84



## Getting started
Steps to follow

1. initialise quantum circuit of sender and reciever//
use function `make_init` 
2. set a random key for sender

using random function of numpy library we choose a key and convert it to binary
3. initialisation a polarisation table

use `sender_polarisation` function to create a polarisation table for sender 

it uses random function and with equal probability it assigns any one of these (↕, ⤢, ↔, ⤡) polarisations to each qubit
4. send qstate to reciever

use the function `send_qstate` it has parameters sender's quantum circuit, reciever's quantum circuit and reciever's quantum register(qubits)
5. initialise measuring basis for reciever

using the function `measure_table` we randomly initialise either rectilinear(✛) or diagonal(✕) basis to each qubit with equal probability
6. add measurements and solve circuit on backend

we use `run_backend` function to add measurement operators to the circuit and run the circuit on quantum backend
7. the final result is the key which the reciever recieves
8. next we compare basis and keep only those indices which have same basis

using the `compare_basis` function we compare the basis chosen by both sender and reciever

since we had initialised polarisations for sender while comparing we assign 

↕ and ↔ as rectilinear basis

⤢ and ⤡ as diagonal basis
9. next we compare the final keys corresponding to those indices if they are same then channel is secure
10. If different there is an eavesdropper and channel is not secure
