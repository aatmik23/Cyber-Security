**Volume Shadow Copy Service (VSS)** is a Windows feature that creates a **snapshot** of your files **at one specific moment**, even if those files are currently being used.

VSS is enabled (**System Protection** turned on), you can perform the following tasks from within **advanced system settings**. 

- **Create a restore point**
- **Perform system restore**
- **Configure restore settings**
- **Delete restore points**

Many types of **ransomware** know about VSS.

Before encrypting your files, they often run commands to **delete all Shadow Copies**.

Why?

Because if shadow copies remain, you might restore your files without paying the ransom.

![](../assets/Pasted%20image%2020260731203824.png)


