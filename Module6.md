**1. What are the pillars of Wi-Fi security?**

Wi-Fi security is built on a few key pillars that ensure safe and reliable wireless communication between devices and networks.

1. Authentication:  
This ensures that only authorized users and devices are allowed to connect to the Wi-Fi network. It verifies the identity of the client using methods like passwords, enterprise credentials, or authentication servers.

2. Encryption:  
Encryption protects the data being transmitted over the wireless network. It converts readable data into a secure format so that unauthorized users cannot understand it. Standards like WPA2 and WPA3 use strong encryption methods.

3. Integrity:  
This ensures that the data is not altered during transmission. It helps detect any modification or corruption of data using mechanisms like message integrity checks.

4. Access Control:  
This controls which devices are allowed to join and use the network. It includes policies like MAC filtering, user roles, and network segmentation.

5. Confidentiality:  
This ensures that sensitive information is kept private and is not exposed to unauthorized users while being transmitted over the air.

**2. Explain the difference between authentication and encryption in WiFi security.**

Authentication and encryption are two important parts of WiFi security, but they serve different purposes.

Authentication is the process of verifying the identity of a user or device before allowing access to a WiFi network. It ensures that only authorized users can connect. For example, when you enter a WiFi password, the network checks whether you are allowed to join.

Encryption is the process of protecting the data that is sent over the WiFi network. It converts the data into a coded form so that even if someone intercepts it, they cannot read or understand it without the correct key. This helps keep sensitive information like passwords and messages safe.

In simple words:
Authentication = checks who can use the network
Encryption = protects the data being transmitted

**3. Explain the differences between WEP, WPA, WPA2, and WPA3.**

WEP, WPA, WPA2, and WPA3 are different WiFi security protocols that were developed over time to improve wireless network protection.

WEP (Wired Equivalent Privacy)
This is the oldest and weakest security protocol. It uses a simple encryption method that can be easily cracked, so it is no longer considered secure and is rarely used today.

WPA (Wi-Fi Protected Access)
WPA was introduced as an improvement over WEP. It provides better security by fixing many of WEP’s weaknesses, but it still has some vulnerabilities and is not very strong by modern standards.

WPA2
WPA2 is a much stronger and more secure version. It uses advanced encryption (AES), which makes it very difficult to hack. For many years, it has been the standard security protocol for WiFi networks.

WPA3
WPA3 is the latest and most secure version. It improves protection even further by using stronger encryption, better password security, and protection against brute-force attacks. It is designed to be safer even when users choose weak passwords.

In short:
WEP = very weak and outdated
WPA = improvement over WEP but still weak
WPA2 = strong and widely used
WPA3 = newest and most secure version

**4. Why is WEP considered insecure compared to WPA2 or WPA3?**

WEP is considered insecure compared to WPA2 or WPA3 because it has many design weaknesses that make it easy to break.

WEP uses an old and weak encryption method called RC4, and the way it generates encryption keys is very simple and predictable. Because of this, attackers can capture network data and figure out the key in a short time.

Another problem is that WEP does not properly protect data integrity, meaning attackers can modify or inject data into the network without being easily detected.

WPA2 and WPA3 fix these issues by using much stronger encryption methods (like AES in WPA2 and improved security protocols in WPA3). They also have better protection against attacks such as password cracking and data interception.

**5. Why was WPA2 introduced?**

WPA2 was introduced to fix the security weaknesses found in earlier WiFi security protocols like WEP and WPA.

WEP was found to be very weak and could be easily hacked, while WPA was only a temporary improvement and still had some vulnerabilities. Because of this, a stronger and more reliable security system was needed.

WPA2 was created to provide much better protection for wireless networks by using a stronger encryption method called AES (Advanced Encryption Standard). This made it significantly harder for attackers to intercept or decode data.

It was also designed to improve data integrity and make wireless communication more secure and stable for everyday use, such as in homes, offices, and public networks.

**6. What is the role of the Pairwise Master Key (PMK) in the 4-way handshake?**

The Pairwise Master Key (PMK) plays a key role in the WiFi 4-way handshake because it is the base secret used to create all other session keys.

When a device connects to a secure WiFi network, the PMK is already known to both the access point (router) and the client device. This PMK is not directly used to encrypt data. Instead, during the 4-way handshake process, it is used to generate a temporary key called the Pairwise Transient Key (PTK).

The PTK is what actually gets used to encrypt and protect the data being exchanged between the device and the network. The handshake ensures that both the client and the access point independently derive the same PTK without ever sending it directly over the network.

**7. How does the 4-way handshake ensure mutual authentication between the client and the access point?**

The 4-way handshake helps ensure mutual authentication between the client (device) and the access point (router) by making both sides prove that they have the correct secret key (PMK) without actually sending it over the network.

Here’s how it works in a simple way:

First, the access point sends a random number (called a nonce) to the client. The client uses this value along with the shared secret key (PMK) to generate a new temporary key.

Then, the client sends its own random number back to the access point, along with a message authentication code (MAC) to prove it has the correct key.

Next, the access point checks this information. If it is correct, it confirms that the client is legitimate. It also generates the same temporary key on its side.

Finally, both the client and the access point confirm that they have successfully derived the same session keys, and secure communication begins.

**8. What will happen if we put a wrong passphrase during a 4Way handshake?**

If a wrong passphrase is entered during a 4-way handshake, the authentication process will fail and the device will not be allowed to connect to the WiFi network.

This happens because the passphrase is used to generate the Pairwise Master Key (PMK). If the passphrase is incorrect, the client and the access point will generate different PMKs. Since both sides rely on the PMK to create the same encryption keys during the handshake, the mismatch prevents them from deriving matching session keys.

As a result, the security checks fail, and the access point rejects the connection request. The device may keep trying to connect, but it will not be able to access the network until the correct passphrase is entered.

**9. What problem does 802.1X solve in a network?**

802.1X is a network access control standard that solves the problem of unauthorized devices connecting to a network.

In many networks, especially in schools, offices, and enterprises, just using a WiFi password is not enough security. If someone knows the password, they can easily join the network. 802.1X improves this by adding strong user authentication before giving network access.

It works using a system called “port-based access control,” where a device must first prove its identity to an authentication server (like a RADIUS server) before it is allowed to access the network. Until authentication is successful, the device is kept in a restricted state.

This helps solve several problems:

  Prevents unauthorized users from accessing the network
  Provides individual user authentication instead of shared passwords
  Allows centralized control of network access in organizations
  Improves overall security in wired and wireless networks

**10. How does 802.1X enhance security over wireless networks?**

802.1X enhances security in wireless networks by adding a strong authentication system before a device is allowed to connect.

Instead of relying only on a shared WiFi password, 802.1X requires each user or device to prove their identity to an authentication server (usually a RADIUS server). This means every user can have a unique login instead of everyone sharing the same password.

Because of this, even if someone knows the WiFi name, they still cannot access the network without valid credentials. The authentication happens before any real network access is given, which prevents unauthorized devices from joining.

It also improves security by:

Allowing centralized control of all user access
Making it easy to remove access for a single user without changing the WiFi password for everyone
Supporting stronger authentication methods like certificates or usernames and passwords
Working with encryption protocols like WPA2/WPA3 to protect data after authentication
