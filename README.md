
---

# **Network Security Project: RSA and ElGamal Cryptographic Algorithms**

## **Overview**

This project demonstrates the implementation of two essential public-key cryptographic algorithms—**RSA** and **ElGamal**—which are widely used in securing communications and data over networks. By utilizing these algorithms, the project showcases encryption and decryption operations, along with key generation mechanisms for secure data transmission.

The project consists of three main files:

1. **`ELgamal.ipynb`**: Implements the classic **ElGamal encryption and decryption** algorithm.
2. **`ELGamal_ECC1.ipynb`**: A variant of ElGamal, utilizing **Elliptic Curve Cryptography (ECC)** for encryption.
3. **`RSA_algorithm.ipynb`**: Implements the well-known **RSA encryption and decryption** algorithm.

---

## **Prerequisites**

Before you begin, ensure you have the following tools and libraries installed:

### **Required Tools:**
- **Python 3.x** (or above)
- **Jupyter Notebook** (or **Google Colab**)
- **pycryptodome** library (for cryptographic operations)

To install the required Python libraries, run the following command:
```bash
pip install pycryptodome
```

---

## **How to Run the Project**

### **Step 1: Setting Up the Environment**
- If you are using **Jupyter Notebook**, run the following command to start a Jupyter server:
  ```bash
  jupyter notebook
  ```
- Alternatively, if you prefer to use **Google Colab**, upload the `.ipynb` files to Colab and run the cells interactively.

### **Step 2: Open and Execute the Notebooks**

#### **A. Running `ELgamal.ipynb` (ElGamal Encryption/Decryption)**

This notebook demonstrates the implementation of the **ElGamal** encryption and decryption algorithm.

**Execution Steps:**
1. Open the `ELgamal.ipynb` file.
2. The notebook generates **public** and **private keys** for ElGamal encryption.
3. A sample message will be encrypted and the encrypted message (ciphertext) will be displayed.
4. The ciphertext is decrypted, and the original message is restored.

**Expected Output:**
- Key Generation Time
- Encrypted Message (Ciphertext)
- Decryption Time
- Decrypted Message (Plaintext)

#### **B. Running `ELGamal_ECC1.ipynb` (ElGamal with Elliptic Curve Cryptography)**

This file expands on the ElGamal algorithm by using **Elliptic Curve Cryptography (ECC)** for enhanced security.

**Execution Steps:**
1. Open the `ELGamal_ECC1.ipynb` file.
2. It will display elliptic curve points and the encryption process.
3. After encryption, the message is decrypted and the receiver's output is displayed.

**Expected Output:**
- Encryption and Decryption Times
- Decrypted Message Received

#### **C. Running `RSA_algorithm.ipynb` (RSA Encryption/Decryption)**

This notebook demonstrates the **RSA** encryption and decryption algorithm, one of the most widely used asymmetric cryptosystems.

**Execution Steps:**
1. Open the `RSA_algorithm.ipynb` file.
2. The program generates **public** and **private keys** using two prime numbers (`p = 23`, `q = 13`).
3. A sample message is encrypted using the generated public key.
4. The ciphertext is decrypted using the private key, revealing the original message.

**Expected Output:**
- Key Generation Time
- Encryption Time
- Decryption Time
- Decrypted Message (Plaintext)

---

## **How the Algorithms Work**

### **ElGamal Algorithm**
1. **Key Generation**: 
   - A prime number `p` and a generator `g` are used. The private key `x` is randomly chosen, and the public key `y` is computed as `y = g^x mod p`.
2. **Encryption**: 
   - A random value `k` is chosen. The ciphertext consists of two components: `c1 = g^k mod p` and `c2 = m * y^k mod p`, where `m` is the plaintext message.
3. **Decryption**: 
   - The receiver uses their private key `x` to recover the original message using the formula `m = c2 * c1^(p-1-x) mod p`.

### **RSA Algorithm**
1. **Key Generation**: 
   - Two prime numbers `p` and `q` are selected, and `n = p * q` is calculated. The totient `f(n) = (p-1) * (q-1)` is also computed. A public exponent `e` is selected, and the private exponent `d` is computed using the extended Euclidean algorithm.
2. **Encryption**: 
   - The message `m` is encrypted using the public key: `c = m^e mod n`.
3. **Decryption**: 
   - The ciphertext `c` is decrypted using the private key: `m = c^d mod n`.

---

## **Execution Times**

Each notebook outputs the following key timings:

- **Key Generation Time**: Time taken to generate the cryptographic keys.
- **Encryption Time**: Time taken to encrypt the message.
- **Decryption Time**: Time taken to decrypt the message and restore the original plaintext.

### **Example Outputs**

#### **ElGamal.ipynb:**
```
Key Generation Time: 0.00001 seconds
Encryption Time: 0.00012 seconds
Decryption Time: 0.00011 seconds
Decrypted message: 105116101
```

#### **ELGamal_ECC1.ipynb:**
```
Encryption Time: 0.003 seconds
The message received by the receiver is: 105116101
Decryption Time: 0.002 seconds
```

#### **RSA_algorithm.ipynb:**
```
Key Generation Time: 0.00009 seconds
Encryption Time: 0.00013 seconds
Decryption Time: 0.00012 seconds
Decrypted message: 105116101
```

---

## **Conclusion**

This project provides a comprehensive demonstration of **ElGamal** and **RSA** encryption algorithms, which are essential for securing data communication. By walking through key generation, encryption, and decryption processes, the project illustrates the fundamental principles of asymmetric cryptography. The use of **Elliptic Curve Cryptography (ECC)** in one notebook further enhances the security of the ElGamal algorithm.

---

## **Future Improvements**

- **ECC-based RSA**: Explore the use of elliptic curves to enhance RSA key generation and encryption.
- **Optimization**: Focus on optimizing encryption and decryption times for larger key sizes.
- **Security Analysis**: Conduct a detailed analysis of the security strengths of each algorithm and potential vulnerabilities.

---
