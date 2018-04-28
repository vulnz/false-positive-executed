
**False positive EXE.cuted. 
False positive problems on legitimate software**  


*This research is made for developers who face false positive results on their software.*

![](https://lh4.googleusercontent.com/nsoFAmXFVwsLQZe6iblHQqbFNaB5Y78d63AcaML0V1WBcplgj_4d-_Wn6iFKOkmXXbgLk4fg2gFtIs3RA_99M-X6xLt8tt8hOd4xwOhQq2DMQDaVvfSWbMecxIDYrS-goXDmeKM3)

### Signature detection:

Many anti-viruses are designed to function analogous to the immune system of a human being. They operate by scanning the computers for available signatures corresponding to the binary pathogens and infections. The anti-virus refers to a dictionary of the known viruses, and if any detail obtained within the file resembles the pattern in the dictionary, then the antivirus neutralizes it. Analogous to the human immune system, the content of the dictionary requires updates like the flu shots to provide considerate protection against emerging strains of viruses. Any anti-virus counteracts to what it deems as harmful. The problem arises concerning the creation of new strains of viruses at a rapid rate at which the antivirus developers may not keep pace. Thus the computer becomes vulnerable during the period between time of detection of the virus and the time the dictionary update is released from antivirus dealers, the reason behind keeping the antivirus updated as up to the current date as possible

### Scan engines Method:

Most importantly, the antivirus’s core function is virus scan engine. The antivirus scans the information, and when the virus is detected, the antivirus disinfects it. Mentioned below are different ways of virus scanning.


#### Main Basic Techniques:

Size: the antivirus easily detects if the file is changed or infected. It is common for some viruses to append their malicious codes at the terminal of the file. An antivirus, in this case, the scan engine scans the file and then compares it prior and after sizes. When the computer user does no changes, the antivirus suspects the presence of malicious actions running on the computer.


Pattern matching: there is a distinct and unique signature corresponding to each virus. The signature is used by the virus to infect files of computers and could be few lines in an assembly language that overwrites the stack pointer rather than jumping to the new line of code. The antivirus compares information with the virus unique signature and presence of resemblance is a clear indication of infection being occurred.

Heuristic occurs when the information being scanned is dangerous without the user knowing whether it contains a virus or not. The technique involves an analysis of the data and then comparing it the list of hazardous actions. For instance, if the antivirus detects that software is attempting to open each EXE file and infecting it by writing a replica of the original program into it, the antivirus recognizes the program and declares it is a dangerous activity and thus sounds an alarm. Now the decision remains to the user whether to eliminate the perilous virus or not.

  

The above methods have merits and demerits. If the antivirus utilizes the signature approach then, it needs to update it regularly. This should be done on a daily basis since at least 15 new viruses emerge in every single day. Thus, if the antivirus is left un-updated for many days, it may cause severe dangers.

Other ways which the antivirus works include monitoring of incoming files and deleting any virus within the files, placing suspect files in quarantine and updating the software produced by the developers so that to address emerging infections. For this case, the software may be set such that it checks for updates at regular time intervals.

## False positives:

False positive is the process of false and positive identification of a computer virus. In false identification, the antivirus identifies a good program as a virus. False positive is regarded as a demerit of virus identification method. Small weaknesses of any virus identification method may result in false positives which are fatal as false negatives.

For an ideal situation, the false positive rate tends to be zero or approximately close to zero. Any small rise in the false positive rate is not desired

  

![](https://lh3.googleusercontent.com/yuvarEQ5Swh9twZHHRQMI1CC73UuSqxvzjs8mvWM7xPoOO1J7R6aujfCooACGSXNIbCbu9X_5g4YhHz4sEaXUfCVVdNQzl9_xJ8ImFcac2JOW4peimJYRDxqyjGXlK9bWSlMfN0m)

*this is a good example of how many percents false positive occur. This is outdated statistics, but idea is clearly seen.

  

### Reasons for getting False Positives:

The particular procedures give very sensitive scanning by determining the relationship between the viruses and their signatures. This type of method has a drawback whereby it is impossible to detect new and unknown viruses. However, generic methods can identify all kinds of viruses without necessarily using virus signatures. The generic methods also have their drawbacks since they create false positives.

  

For instance, the heuristic can detect new and unknown viruses though they are prone to false positives. This is as a result of the method adopted by heuristics relies on probabilistic methods and are therefore not certain of an infection.

For example, if a heuristic program identifies a file “open” prompt, followed by “file read” and “write” prompts, and also identifies a string “Virus” within the program, then it can respond that the file is under attack of the unidentified virus.


There are chances that a file which is infected by a virus may meet all the conditions that render it infected; this is what results in false positives.

 
As mentioned generic methods are the most susceptible to false positives.

False positives may result due to the complications that arise in determining the disparity between codes that are good and bad. Making wrong decisions may result in false positive or false negative. The antivirus functions to solely find signatures of viruses and not the whole of the virus program. It also looks for wildcard signatures. The signatures that the antivirus finds may not necessarily be of virus codes only.

Since the conventional signature is redundant when handling polymorphic and metamorphic malware, antiviruses with new technologies should incorporate heuristic approaches in dealing with such viruses. Such methods are often faced with high rates of false positives.

  
**Solutions:**

1.  All software should have basic information that has binary file: Description, Version, Product name, Language, Company name. Many false positives are made because file does not have any information inside, so it flagged as suspicious or unwanted.
    

![](https://lh5.googleusercontent.com/P7qpH3CumfNVcbv_pVndpPqpAW7maD209O-msuXm4kG-Ia1loMm9pXVzh1hYwfzp5oFFtOyT5ba0kTRE2oEhdA1y7gRny5lOZcUlMWg42x2R19NfAfxlroVpgY4_vxFwnsw_MoLg)

  

2.  We need to check if file flagged as virus based on its md5, it is very uncommon situation, but it can accidently happen, but here is an [example](https://www.mathstat.dal.ca/~selinger/md5collision/) how it can happen.
    

3.  We need to pack exe in order to make it harder to depack it.
    

In this case we need to use custom packet, but in other hand it is better to pack it using standard UPX because creating custom pack can cause new problems for antiviruses that will not be able to identify which type of packer was uses.

![](https://lh3.googleusercontent.com/i7XsbDtAWtEHSdR0E9yDaPsFSy_8cYE-Aq1zlc9O3GLZCNpHZ3LPI2uO3GZtgqorL60lFi7DsQaj1xz3oVIYg1m4RTR6hwmh4DqyZzattI8fXtkOKk5qmAUC4QWdPiAX7bTbRTh7)


Antivirus's trust commonly used packers and do not like custom packers or some kind of antivirus packers.

4.  We have to avoid using hooks that write them self or read from registry if we dont need it. Here is a list of suspicious registry calls that should be avoided:
    

call for: antivirus software, firewall, remote administation, keyboard layout, extentions change, update enable/disable, look/edit system journal.

  

![](https://lh6.googleusercontent.com/CV3F6_PHwFa3Ou0RAl-_DTcMn3meqUQPM1VlSxPy1dzPEb9_Liud8bwCsM24vRrP07qXxPZ2oG3kMsW2YkNIMqoqeNWhWoONcTeiF9C_jcpCFEKVqjX5rbVCQ9vswAeBe0R1woq5)

  
5.  We have to avoid using system files and services that work with remote administration or connections if we do not develop network software.
    

Calling integrated software like: ftp, telnet, psexec ,rdp or other inside our binary can cause false positive because a lof of malicious software use integrated ftp client as an example to steal and transfer data over the internet. It is better to use system tools, not system software.

  

![](https://lh6.googleusercontent.com/MYyKuiItA-Tu5C_zMBY3194EqzFsSccCdH8hLjIB0HDc-0SNq_PaYSoJKZ2k7ftpQ9IffrBkE98gwF8kRT523NQNRXhAWoXYHepvKOpgd6bLIhZYSFBTiVkZnE3qFg_OY6J5ayWt)


6.  It is a good idea to create msi packer for installing and uninstalling software.
    

[Here](http://www.silentinstall.org/) is an example of how to create msi packages. It was also checked that antivirus's trust more msi files because they mostly used with good purpose and bypass behavioral analysis better.

![](https://lh5.googleusercontent.com/-3IyB1Edg_RmL0WUXZPaL0L-yHn6xoWwEDfbRo447V-AHI4LwvbeVwRWYLHedHQemaKKJm5olyGs_hTecbZWGq9QEf92DzLeQGPur1FG9nJ4yX0d0kVi6bTen0vk8QWq5oSiXVHo)

* example of terminal utility to pack exe to upx.


7.  We can give ability to check if compiled binari is flagged as malware using virustotal database right away and give advices.
    
8.  Can be useful to avoid reverse if someone who develops want to avoid reversing of his code - enable anti virtualbox/sandbox solutions with virtualenv detection.
    
 
9.  Avoid comunity from creating malicious software. Talk to community and make weekly research on github and other websites in order to see if someone created malicious software. This will make antivirus companies look deeper and maybe give more false positives. This happened with Develstudio project. Develstudio is a project created to create gui or binary from php code. Based on research this project almost closed and lost big amount of followers because it was used for malware creating, not php2exe clean projects creation. Algorythm can be as simple as this: find all projects simmilar projects on github, download them to cloud and check all releases (binary) for viruses. To make it more complex - compile and check. This is not hard if community is not big. [Here](https://github.com/yolofy/AvScan) can be found wrappers for common viruses, so it will make it easier to work with them, not only checking it on virustotal.
    

10.  Better not to use common names of windows core files was found that some antiviruses found common names like “svhost.exe”, “system32.exe”, etc
    

11.  Better not to use names of commonly used software like: “firefox.exe”, “chrome.exe”, etc. It was proven that 3-5% of antiviruses react on this type of names rechecking md5 of real products and their versions and this binary.
    
12.  One of the most important procedures on software development is approvement and it was checked that all binary software that is not signed in or flagged on antivirus server as commonly used will be blocked by browser or windows smart screen.
    

[Here](https://blog.jayway.com/2014/09/03/creating-self-signed-certificates-with-makecert-exe-for-development/) is automated sollution with bat file that can be perform in order to sign up  software. [Here](https://www.digicert.com/code-signing/signcode-signtool-command-line.htm) is a commercial utility and project where can be bought cert and software to sign up builds.

13) Do not put multiple exe inside one. This type of activity is common for trojan horse, so why it is important to understand that archiving one binary inside other for some reasons can cause problems.

![](https://lh5.googleusercontent.com/_m622KtVzcYlBhMWEolNnIK2aXvChDLRw8Da2bAxmte0zevue-Pg6O3GoxNDymDpk_1E_IWriQwfKIwQoaHu_L7cJhvXDMoTB-9dxM-O-rZ3YN6FbC3Y3dbt9BANggF-pUMU7CA5)

*this is example of exe joiner that marked as malicious even without being so only because it is commonly used to glue down some malicious software, so it’s algorithm marked as malicious too.

 
14) It was found that some binary have a big amount of ZERO following by each other. For antiviruses it could be understood as problematic software because it creates specially unused area in memory or on harddrive in order to: bypass md5 check, bypass some behavioral analysis, bypass signature based analysis, so it is important to make code where no lines of zeros could be found on hex editor.

  

![](https://lh3.googleusercontent.com/5wckAhQeG8fnZX-8a2S9VYdEarm-SPfzo4to-hyozhkGkDCPQR-IVNKny3eVHEdnuBuCm4uJr-9kCxgxNQxv1DTC6jC1hfV0hcfJmeNWUumyyXYafcJQH8sAeffduN2novquhvUK)


15) It will be a great idea to allow users to read terms and conditions before they install software or run it. There is no information confirmed about antiviruses check for existence of terms and conditions, but


16) Custom icon for binary file is one of reasons it may not be detected as malicious. As was told before there are machine learning techniques that give information about “HOW malware should look like” and most of malware by itself do not have any ico, because their developer steal ico, which is detected by antivirus as well or do not create one, leaving it standard.


17) Do not use special characters or big amount of white spaces or dots on name. It was checked many times with different antiviruses that for purpose of defense from extension spoofing names that violate certain rules will be blocked and marked as malicious. It is easy to check creating clean exe with spoof name.

[Here is software.](http://atksoftware.blogspot.com/2015/03/file-extension-spoofer-download.html)

  
18) Files that download other files or source from internet and run it. This looks like a bit problem for some antiviruses as long as they can not control all process, so why they may mark this actions as suspicious.

19) Files that download and run libraries can be flagged as dangerous because based on machine learning some .dll files can be used in massive development of malicious software and you can be one accidentally using it. It is always better to use OS integrated software


20) Try not to inject into running process because as was mentioned before many antivirus solutions can see hooks or injectors and mart them suspicious even if they do not do any harm.

Signature creation process:


It was found a [good article](https://github.com/Cisco-Talos/clamav-devel/blob/master/docs/signatures.pdf) where it can be found everything about creating signatures for viruses for ClamAv. This article was read and baes on it we put some additional information above.

  
 
**Solving problem:**

It can be developed software that will detect if binary was compiled by compiler and help it to bypass all problems step by step, or can be integrated inside compiler ( not sure it is a good idea bases on size that will be increases. All steps could be found above.

Idea is to make easier life for developers who want to distribute their software but constantly face problems with false positive. This can be different product from but it can be put like “tools” that help developer with this issue.

  

![](https://lh3.googleusercontent.com/7jKZ9OQvRFRHVk6CeSDv-SqkRJloFicnGOjOZpIdYoexwR0cbN-nt8n5tuRJmvaE7bMo_Qzah6FHsaW10qq9Bw8FWEyTSP8x7acicFNq2_7-L0z-N4M8PeqpWR4G1cfaJHzu2oOu)

*example of how can exe maker/wrapper look like that can help to bypass false positives.

**To summarize all information given before, here is what antivirus engineers answer on why false positive occur.  Some comments on why false positives run on their antivirus solutions:**

  

![Картинки по запросу antivirus](https://lh5.googleusercontent.com/mxqUnXPvq-9aXt9hqXiwwV15u8R4d5Mhmio0ewwkvLuZGwrHUKbw2F8M8w6Y-TAA3RWRQa0Y2p7b6u7IPgfqqclzm6SOdSYi4NZ-AKi6kwfbGEoOqX_5GoMK7MG1ImGb0SQlMsEf)


*The most important information were highlighted.

## Ryan Permeh, Cylance:

## ![Картинки по запросу Cylance](https://lh5.googleusercontent.com/AUfCQRh5YL2AINHRPZ5abhLz65gxPA_xpjamnoiCnPl9HwmAxNVHeQRPKJmJwY72JZXD7_55kcOUlNNPJGfE8OVDITvaH3sZ3Czqr0qSxS351dL3h1pAWm5taVwMw71D_jdAhuuY)

"The Cylance engine is not an antivirus engine. Unlike AV, it doesn’t have a bias toward letting everything run. The technology doesn't assume a file is good until it’s evaluated. Our approach is to measure and decide on each and every file individually, and if it doesn't fit into our model of good, it leans towards bad.

"Without a bunch of data to base a decision on, and without any real patterns of goodness to identify it as such, the engine leaned heavily on the structural bits that are odd and drew a line towards bad in this case.

"When we train models, we train on hundreds of millions of good and hundreds of millions of bad files (samples). We look at several million potential data points (features) in each file...

"...In general, a piece of code can become "bad" by doing things that lean towards bad. But it can also lean towards bad by not doing things that lean towards good. So in the most basic example provided (hello world in debug build):

"The sample was small. It didn't show any bad, but it didn't show any good either; One function programs are almost always malware; Debug builds are statistically weird; Using mingw rather than visual studio is statistically weird. The output binary is 'odd.'"

  

## Hyrum Anderson, Endgame:

## ![Картинки по запросу Endgame antivirus](https://lh3.googleusercontent.com/N5quojKBxvg-jiNFLXLCSUJiMgFyM0p9jyOBWPJD1JCvxtAAt6caKorBBpHNEYn_MBrSaMHtRVrKKOwxYTkin4DvBmf8dbg_ElRB2bd1mlx4icOWyAqR-ZE5FeHpaJspq9e4f8WU)

"Before Twitter caught ablaze with these “hello world” samples, our own internal research indicated that our and other models were susceptible to these toy samples. Let’s explain why.

"Endgame’s machine learning malware detection uses static features to determine before a customer executes a file whether it is likely malicious or benign. The machine learning model is an imperfect summarization of tens of millions of malicious and benign software on which the model was trained.

"As an imperfect model, it can obviously be wrong, but still extremely useful in detecting never before seen malware, far more useful than approaches which rely on signatures for already known malware families.

"For the case of our model and other machine learning models based on static features, the model can be wrong in this case because, in the training dataset, the model has seen:

"Lots of real malware samples that are small unsigned binaries; lots of real malware samples where the entry point (.text) section is small, like droppers unpacking stubs; lots of real malware samples that attempt to hide their imports from static analysis by some method, so that their import table looks very small.

"On the contrary, there are very few “useful” benign files that are small, certainly too few to contradict the above experience.

"It’s important to note that machine learning is actually quite good for prevention and detection malware, both novel samples and the more well known. Endgame was one of the only few to get NotPetya in VirusTotal, for example. That said, all machine learning models have blind spots (false negatives) and they can mistakenly call things bad (false positives). In fact, we’ve shown in our published research that for some machine learning models, these vulnerabilities can be quite convenient to exploit...

"...At Endgame, we employ a strategy of layered protections that align with a large number of commonly seen attacker actions. Our MalwareScore engine (released standalone in VirusTotal) represents only a single slice of that layered protection paradigm. The layers work in concert to alert our customers of potential threats (reducing FNs), and working together to build a complete story of a potential threat (reducing FPs).

"Fortunately, the samples highlighted on Twitter are interesting corner cases, but are extremely esoteric for our customer base. Nevertheless, we continually are doing more research to improve our detection ratio and reduce our false positive rate. This involves data gathering to increase our model’s understanding of the universe of benign and malicious software as well as a huge amount of experimentation effort to maximize our model’s performance. We put a great amount of attention on addressing known false positives seen by our customers. As a result of these efforts, we regularly release models to our customers and to VirusTotal. And, we continue to work with 3rd parties to validate our model’s performance on real files.

  

## Dr. Sven Krasser, CrowdStrike:

## ![Картинки по запросу CrowdStrike](https://lh4.googleusercontent.com/o9NoFZ81BZ_j0Tim9GKYt9nihZqFia1OFZ8LdgnhAlbyPE70MTHFACD5F_WddAyuyhzzjyhiU_KkcVCRLsRwlwVtXrm46NaRghSF2d4IzFB8i7T8X8D-AjaLC-clh4UjNFYUhnF8)

"There are two important aspects to understand. First, the machine learning models for static file analysis we use at CrowdStrike are optimized to detect malware, especially novel families that bypass signature-based approaches, while avoiding interference with legitimate business applications. However, unusual and artificially constructed files fitting into neither of these two categories are occasionally detected as well.

  

"For this reason, we expose confidence values and allow customers to set their own thresholds. While in this instance our file analysis engine was arguably too aggressive, generally this behavior is by design: if a file does not look like a legitimately useful application while also exposing unusual traits, then the sound call is to prevent it from executing.

  

Avoiding odd looking yet potentially benign objects should be a familiar concept should you have ever opened an office fridge before.

"Second, static file analysis alone (i.e. what most vendors provide on VirusTotal) is simply not a sufficient security tool on its own. It is easy to create files that behave benignly yet are detected by both signature and ML-based engines.


It is, however, also possible to create malware files that bypass detection. That is trivially possible for signature-based engines, but one can also bypass ML-based static file analysis with some effort. Therefore, CrowdStrike Falcon uses static file analysis as only one of many techniques to detect threats while combining it with several other layers of defense, such as advanced Indicators of Attack."

[List of antivirus companies for false positive submitting](https://docs.google.com/spreadsheets/d/1vsPEXvHLDLllPk_yA-yDpx-Xc99-sSHsvi_sVYCOQSQ/edit#gid=0)
