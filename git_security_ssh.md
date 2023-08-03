### Git Security SSH

> #### Git Security
* Up to this point, we have used HTTPS to connect to our remote repository.

* HTTPS will usually work just fine, but you should use SSH if you work with unsecured networks. And sometimes, a project will require that you use SSH.

## What is SSH

SSH is a secure shell network protocol that is used for network management, remote file transfer, and remote system access.

SSH uses a pair of SSH keys to establish an authenticated and encrypted secure network protocol. It allows for secure remote communication on unsecured open networks.

SSH keys are used to initiate a secure "handshake". When generating a set of keys, you will generate a "public" and "private" key.

The "public" key is the one you share with the remote party. Think of this more as the lock.

The "private" key is the one you keep for yourself in a secure place. Think of this as the key to the lock.

SSH keys are generated through a security algorithm. It is all very complicated, but it uses prime numbers, and large random numbers to make the public and private key.

It is created so that the public key can be derived from the private key, but not the other way around.


### Generating an SSH Key Pair

In the command line for Linux, Apple, and in the Git Bash for Windows, you can generate an SSH key.

Let's go through it, step by step.

Start by creating a new key, using your email as a label:

```cmd
ssh-keygen -t rsa -b 4096 -C "test@w3schools.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/user/.ssh/id_rsa):
Created directory '/Users/user/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/user/.ssh/id_rsa
Your public key has been saved in /Users/user/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:******************************************* test@w3schools.com
The key's randomart image is:
+---[RSA 4096]----+
|                 |
|                 |
|                 |
|                 |
|                 |
|                 |
|                 |
|                 |
|                 |
+----[SHA256]-----+
```

* You will be prompted with the following through this creation:

```cmd
Enter file in which to save the key (/c/Users/user/.ssh/id_rsa):
```

* Select a file location, or press "Enter" to use the default file location.


```cmd
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

Entering a secure passphrase will create an additional layer of security. Preventing anyone who gains access to the computer to use that key without the passphrase. However, it will require you to supply the passphrase anytime the SSH key is used.

Now we add this SSH key pair to the SSH-Agent (using the file location from above):

```cmd
ssh-add /Users/user/.ssh/id_rsa
Enter passphrase for /Users/user/.ssh/id_rsa:
Identity added: /Users/user/.ssh/id_rsa (test@w3schools.com)
```

You will be prompted to supply the passphrase, if you added one.

Now the SSH key pair is ready to use.


### Git GitHub Add SSH

> #### Copy the SSH Public Key

In the previous chapter, we created an SSH key pair.

Now we will use the clip < command to copy the public key to our clipboard:

```cmd
clip < /Users/user/.ssh/id_rsa.pub
```

Go to GitHub, navigate to the top left corner, click your profile, and select: Settings:

![show ho to do](https://www.w3schools.com/git/img_github_profile_settings.png)

#### Then select "SSH and GPG keys". and click the "New SSH key" button:

![img to show](https://www.w3schools.com/git/img_github_profile_settings_ssh.png)

* Select a title, and paste the public SSH key into the "Key" field, and click "Add SSH Key":

![img](https://www.w3schools.com/git/img_github_profile_settings_ssh_add.png)

You will be prompted to supply your GitHub password.

You will see your new SSH key added:

![img](https://www.w3schools.com/git/img_github_profile_settings_ssh_added.png)

#### Test SSH Connection to GitHub

Now we can test our connection via SSH to GitHub:

```cmd
ssh -T git@github.com
The authenticity of host 'github.com (140.82.121.3)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com,140.82.121.3' (RSA) to the list of known hosts.
Hi w3schools-test! You've successfully authenticated, but GitHub does not provide shell access.
```


### Add New GitHub SSH Remote

Now we can add a new remote via SSH to our Git.

First, get the SSH address from our repository on GitHub:

![img](https://www.w3schools.com/git/img_github_repository_code_ssh.png)

Then use that address to add a new origin:


```cmd
git remote add ssh-origin git@github.com:w3schools-test/hello-world.git

```

> *** Note: You can change a remote origin from HTTPS to SSH with the command: 
> ***git remote set-url remote-name git@github.com:username/repository.git***

```cmd
git remote set-url origin git@github.com:w3schools-test/hello-world.git

```








