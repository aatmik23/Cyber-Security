
The answer would be in using security models. In this task, we will introduce three foundational security models:

- Bell-LaPadula Model
- The Biba Integrity Model
- The Clark-Wilson Model


### Bell-LaPadula Model

**Simple Security Property** : 
“no read up”
lower secuirty level cannot read at upper secuirty level

**Star Security Property** :
"no write down"
higher secuirty level cannot write down lower secuirty level

**Discretionary-Security Property** :
roperty uses an access matrix to allow read and write operations

|Subjects|Object A|Object B|
|---|---|---|
|Subject 1|Write|No access|
|Subject 2|Read/Write|Read|
“write up, read down.”

limitations to the Bell-LaPadula model.
For example,
it was not designed to handle file-sharing.


### Biba Model

achieve **integrity** by specifying two main rules:

**Simple Integrity Property** : 
“no read down”;
a higher integrity subject should not read from a lower integrity object.

**Star Integrity Property** : 
“no write up”
; a lower integrity subject should not write to a higher integrity object.

“read up, write down.”

Biba Model suffers from various limitations. One example is that it does not handle internal threats (insider threat).


### Clark-Wilson Model

aims to achieve integrity

**Constrained Data Item (CDI)**

data type whose integrity we want to preserve.

**Unconstrained Data Item (UDI)** :

data types beyond CDI, such as user and system input.

**Transformation Procedures (TPs)** :

programmed operations, such as read and write, and should maintain the integrity of CDIs.

**Integrity Verification Procedures (IVPs)** :

procedures check and ensure the validity of CDIs.