# Daily Challenge → Day 3: Git processes and Version Control

Welcome to **Day 3** of the **Daily DevOps & SRE Challenge – Season 2!** 🎉  

Here we will understand how to work on a shared repository, create branches, make changes, resolve merge conflicts, and handle pull requests across both GitHub and GitLab.

# Installing Git on Windows
    1. Go to link- https://git-scm.com/downloads and download it as per your system.
    2. Enable Git bash
    3. Inside Git bash run the command
    Git --version
Output:
    ![Version](./Proof%20of%20work/Version.png)

### Configuration of Git
    1. Use Command 
        git config --global user.name   "Soumya"- To commit the name of Author.
        git config --global user.email "soumya@demo.com"- To commit the Author's email id.
Output:
     ![Config](./Proof%20of%20work/Config.png)
## SSH Key Setup

    1.Inside Git Bash use command:- 
        ssh-keygen -t rsa -b 4096 -C "soumya@demo.com" (In inverted put Author's email id)
    2.To accept the default path press enter    
Output:
 ![SSHkey](./Proof%20of%20work/SSH.png)

 ## Let's start the Agent
    1.Pass the command- eval $(ssh-agent -s)
        a.This command will start the SSH agent in the background.
        b.This is like a program that stores our private keys in memory, so we don’t have to type the passphrase every time we use the key.
    2.Then use the command- cat ~/.ssh/id_rsa.pub
        a.This adds your private key (id_rsa.pub) into the ssh-agent.
Output:
    ![SSHconf](./Proof%20of%20work/SSH%20Conn.png)
        b. Add the above to your Github SSH Key

![gitco](./Proof%20of%20work/githubco.png)

    Then edit the SSH config for Github.
    Open the config fie
        vi ~./ssh/config
    Then Add the below content
        Host github.com
            HostName github.com
            User git
            IdentityFile ~/.ssh/id_rsa    
    I added as per my naming convention.

If here any issue you face then rectify it and restart the ssh-agent.

Then add the private key with command-
     ssh-add ~/.ssh/id_rsa

Expected Output:
![EO](./Proof%20of%20work/expectedop.png)

One part is hidden and one part is highlighted.
The part which is highlighted in orange is the expected output.

## ✅ Community Links

* **Discord** – [Join here](https://discord.gg/mNDm39qB8t)
* **Google Group** – [Join here](https://groups.google.com/forum/#!forum/daily-devops-sre-challenge-series/join)
* **YouTube Channel** – [Subscribe here](https://www.youtube.com/@Sagar.Utekar)

---

## ✅ Conclusion

This challenge gave me hands-on experience with Git workflows on both GitHub and GitLab. Using Git on Windows, I learned how to create branches, commit changes, resolve conflicts, and collaborate effectively. These skills are essential for working in DevOps and SRE roles, and this challenge helped build confidence in using version control systems in real-world environments.

---

**Happy Learning!**
– Soumya