SECURING PASSWORD CREDENTIAL DATABASES

1) General Introduction 
 
The Password Problem: Easy Targets, Big Risks 

Imagine our online life: emails, bank accounts, social media, and more. All protected by passwords, acting as the keys to your digital world. But what if those keys were easily copied, stolen, or cracked? Unfortunately, traditional password storage methods like plain text and simple hashing leave user data vulnerable to attackers. Simple hashing scrambles passwords, but attackers can use pre-computed lists called rainbow tables to crack them quickly. This puts sensitive data at risk, leading to: 
 
•	Identity theft and financial loss: Stolen credentials can be used to access and exploit your accounts 

•	Data breaches and reputational damage: Companies with compromised databases face hefty fines and lose public trust.

We need a better way to secure passwords, protecting both users and their data. 

Introduction to Hash Algorithms: 
Hashing is described as an algorithm that transforms strings into random characters, operating as a one-way function without a key for decryption. Hashing is commonly used for security in the authentication process, ensuring the validity of information transmission. 
Hash Usage in Information Systems: 
Hashing techniques are employed in various authentication processes, including login authentication, file authenticity, password storage, key generation, and more. MD5 and SHA1 are common hash functions, but their vulnerabilities, including susceptibility to attacks, are to be noted. 
 
What is Salting? 
During password registration, a unique, random string of characters (salt) is generated. This salt is appended or prepended to the user's password before applying the hash function. When the salted password is hashed, the resulting output (salted hash) becomes completely different from the hash of the original password. 
How ‘Sign in’ and ‘Sign up’ works for hashed passwords with salts ?? 

Sign Up: 

•	We enter our desired username and password.(eg:Secret123) 

•	The server generates a random salt, let's say "abc", and combines it with our password, resulting in "abcSecret123". 

•	The website or app takes our password and converts it into a "hash." It's created using a special algorithm (like SHA-256 or MD5). 

•	The website or app stores our username, salt and the hash of our password in its database. It doesn't store our actual password, just the hash. 

Sign In: 

•	When you try to sign in, you enter your username and password. 

•	The server retrieves your stored salt "abc" from the database and combines it with the password you entered, resulting in "abcSecret123". 

•	The website or app takes the password and hashes it using the same algorithm. 

•	It then checks if the hash of the entered password matches the hash stored in the database for your username. 

•	If the hashes match, it means you've entered the correct password, and you're allowed to sign in. 
 
 
1.Brute Force Attack : A brute force attack attempts to guess a password by systematically trying every possible combination of characters. This method is exhaustive, iterating through all combinations of letters, numbers, symbols, and uppercase/lowercase variations until the correct password is discovered. 
Strengths: Brute force attacks are guaranteed to find the password eventually, regardless of its complexity. 
Weaknesses: This method is extremely slow, especially for passwords with many characters or complex variations. It becomes computationally infeasible for very long passwords.

2.Dictionary Attack : A dictionary attack leverages a list of commonly used passwords or phrases. This list might include words found in dictionaries, common names, keyboard patterns, and leaked password databases. The attack attempts each password in the list against the target system. 
Strengths: Dictionary attacks are significantly faster than brute force attacks, especially when targeting users who choose weak passwords. 
Weaknesses: This method only succeeds if the password is present in the dictionary. Strong passwords with unique characters and variations are unlikely to be cracked through this method.

3.Rainbow Table Attack : Rainbow table attacks utilize pre-computed tables that map possible plaintexts (passwords) to their corresponding hashed values. These tables are created offline using complex algorithms and require significant storage space. During an attack, the attacker compares the hashed password obtained from the target system to the pre-computed hashes in the rainbow table. 
Strengths: Rainbow table attacks can be very fast for cracking passwords of specific lengths, as they eliminate the need for real-time calculations. 
Weaknesses: These attacks are limited by the pre-computed table's size and scope. They only work for password lengths the table covers, and creating tables for complex passwords is resource-intensive. 

2) Problem Statement 
Traditional dictionary attacks rely on predefined wordlists, which often lack the diversity and complexity required to effectively crack passwords in modern security scenarios. The objective of this project is to enhance the effectiveness of dictionary attacks by creating a robust and comprehensive wordlist through the integration of various techniques such as Custom Word List Generator using scrapping, Spidering, Common User Passwords Profiling, Mangling rules, and other relevant methodologies. 

3) Significance Of the Problem   
 
Improved Password Security: By enhancing the efficiency of dictionary tables through PassGAN, organizations can better assess the strength of their passwords. This can lead to the identification of weak passwords that need to be strengthened, thereby improving overall password security.  

Offline Attack: It plays a significant role when it comes to offline attack on passwords where we don’t have any restriction of number of attempts like that of online. It is quite useful in case we have any encrypted data file stored in the hard disk. 
 
Enhanced Password Recovery(Password Retrieval): In the event of a forgotten password or a security breach where password recovery is necessary, an enhanced dictionary table can speed up the recovery process. This can minimize downtime and disruptions to operations, ensuring continuity in business processes.  

Proactive Security Measures: The project encourages organizations to proactively assess their password security practices by leveraging advanced techniques like PassGAN. This proactive approach can help prevent security breaches before they occur, reducing the risk of data breaches and associated costs. 

Compliance with Security Standards: Many industries and regulatory bodies require organizations to implement strong password security practices. By enhancing dictionary tables, organizations can better meet these standards and ensure compliance with relevant regulations. 

Educational Value: The project can also serve an educational purpose by highlighting the importance of strong password practices and the role of advanced technologies in enhancing cybersecurity. This can lead to a broader understanding and adoption of secure password. 

4) Solution Approach

My solution approach combines several stages to systematically generate enriched password lists, leveraging a combination of data scraping, password profiling, mangling rules, and machine learning techniques. Here's a brief overview of each stage: 
 
Custom word list generator for Data Scraping: Utilize custom word list to scrape textual data from the LinkedIn or Twitter profiles of target users. This includes profile descriptions, posts, comments, and other relevant content. 

Password Profiling Method: Input the scraped data into Common User Passwords Profiler method. Password profiling analyzes the user's personal information, such as name, date of birth, and interests, to generate personalized password lists. 

Mangling Rules: Apply mangling rules to the output of the Password Profiling method. These rules include permutations, substitutions, character additions, and other transformations to increase the complexity and coverage of the password lists. 

GAN Training: Train a Generative Adversarial Network (GAN) using the enriched password lists generated from the previous steps. The GAN learns the underlying patterns and structures of passwords and generates new password candidates that mimic real passwords. 

Evaluation and Refinement: Evaluate the quality and effectiveness of the generated password lists using metrics such as password strength, entropy, and coverage. Refine the pipeline based on the evaluation results, adjusting parameters, adding additional data sources, or improving the training process to enhance performance practices across organizations. 

5) Modeling and Implementation Details
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/b1888fe6-0522-4753-8392-45738819b977)

![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/923f2e50-05c5-4ea5-8cb6-d63ce33c9403)

6) Output Snapshots

GOAL 1: Comparing password cracking time when hashes are manipulated by using three different type of schemes. 
 
RESULTS: 
Scheme 1 took least time which shows that it is not that much safe. 
Scheme 2 took more time than scheme 1. 
Scheme 3 took more time than scheme 1 and similar to scheme 2. 

![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/a350f02a-c228-44de-bc54-2481b0f9f9e1)

![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/8e9c0406-851c-49a3-88dd-ed6a40e9cf82)

![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/efbb0c9a-fa25-405b-ab2d-a2a9b6c69357)

![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/447fbca1-2250-4221-a818-dd37badc006a)

GOAL 2: Comparing all three attacks in terms of their speed and working characteristics 
 
RESULTS: 
Brute Force : It was quite slow while cracking any password as it will generate all possible combinations. 

Dictionary : It was faster than brute force attack. 

Rainbow Table: It was faster than brute force and especially for specific lengths. 
 
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/6d4086dc-2a5d-4857-b510-60a9177687e0)
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/6a94da5e-92d8-41d9-b265-3af13f88d281)

GOAL 3: Analyzing Dictionary Attack when dictionary is already provided 
 
RESULTS: Dictionary Attack generates a POT file that contains hashes and successfully cracked passwords 
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/4a46b358-dab9-4c6c-9ebd-b9c86d828807)
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/929cfaad-30a0-4e92-a066-7b21589db91c)

GOAL 4: Wordlist generation based on spidering by using crawling technique for sports oriented passwords along with customized rules. 
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/3df3ebdf-a9b4-4a75-bf47-8fcc9864f67c)

GOAL 5: Spidering and Collecting Victim’s Information 
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/b79f73d6-ec99-41c3-b395-592204ff22be)
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/77523c1c-6a4f-4ce0-8ecb-460c6b98f9f9)

GOAL 6: Finding Victim’s background 
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/cb8f1dad-3be4-46f7-baa5-984c03d9ee2d)
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/ce61afb9-59d2-4a8b-99ab-68bf401033c7)

GOAL 7: Finding crucial information based on other accounts where the victim has used the same email/mobile no for sign up. 
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/d0619f4a-9de4-47f0-913e-f9f7d569cab6)

GOAL 8: Wordlist generation based on spidering by using crawling technique for sports oriented passwords along with customized rules.
![image](https://github.com/NavyaSingh2003/securing_password_credential_databases/assets/110404553/0b8d9d32-9e5b-4258-b754-9679ca29e507)

GOAL 9: Pseudo code of Password Profiling   

Procedure PASSWORD PROFILING(): 
Initialize wordlist as an empty list 
Prompt user for personal information (e.g., name, birthdate, pet name, etc.) 
Prompt user for password policy requirements (e.g., minimum length, required characters, etc.) 
Generate password variations based on user-provided information and policy requirements: 
For each category of information: 
For each possible combination of that category: 
Append variations of that combination to the wordlist 
Save the generated wordlist to a file 
Output success message to the user 
End Procedure 

GOAL 10: Pseudo code of Custom Word List Generator using scrapping 
 
Procedure custom word list generator using scrapping(url, depth, min_length): 
Initialize wordlist as an empty list 
Initialize visited_urls as an empty set 
Add url to visited_urls 
Crawl the website starting from url up to depth levels: 
For each page in the website: 
Extract text content from the page 
Tokenize the text into words 
Filter out words shorter than min_length 
Add unique words to the wordlist 
Save the generated wordlist to a file 
Output success message to the user 
End Procedure 

GOAL 11: Pseudo code of Crunch 
 
Procedure Crunch(min_length, max_length, character_set, output_file): 
Initialize wordlist as an empty list 
Generate all possible combinations of characters within the specified character set: 
For each length from min_length to max_length: 
For each combination of characters of that length: 
Add the combination to the wordlist 
Write the generated wordlist to the output_file 
Output success message to the user 
End Procedure 

