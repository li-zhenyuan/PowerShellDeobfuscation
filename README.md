# PowerShellDeobfuscation


**Zhenyuan Li**, Qi Alfred Chen, Chunlin Xiong, Yan Chen, Tiantian Zhu, and Hai Yang. 2019. **Effective and Light-Weight Deobfuscation and Semantic-Aware Attack Detection for PowerShell Scripts**. In Proceedings of the 2019 ACM SIGSAC Conference on Computer and Communications Security (**CCS ’19**). \[[PDF](https://www.researchgate.net/profile/Zhenyuan_Li2/publication/335927735_Effective_and_Light-Weight_Deobfuscation_and_Semantic-Aware_Attack_Detection_for_PowerShell_Scripts/links/5de75d36299bf10bc33d6f2f/Effective-and-Light-Weight-Deobfuscation-and-Semantic-Aware-Attack-Detection-for-PowerShell-Scripts.pdf?_sg%5B0%5D=A-6bdztnWi9tFp_tDqeVv3lKT4u-fOn-jGBfJJreVgnAJWqrbDs8lYdo9Osv8_DcNijArJpHaFjXbKBlwn2OnA.fV-asa-FXOW4XLL5crw0X-93A2cTXyixIJgyRO4hG1fJrzqSSIudxM81IYHMilcJzNAftaKWui83NmGvaLKgPw&_sg%5B1%5D=-swOG3Gs80SQHb_fX4QoXmh-7-9fm2Lt6d1sT5R-zb62j97cU9GwvQ_R38CWSRAA0NRKupNaoo19WOHLVuqaS5lJnrz6UA0PPtCA7UG_Isya.fV-asa-FXOW4XLL5crw0X-93A2cTXyixIJgyRO4hG1fJrzqSSIudxM81IYHMilcJzNAftaKWui83NmGvaLKgPw&_iepl=)\]


## Abstract
In recent years, PowerShell is increasingly reported to appear in a variety of cyber attacks ranging from advanced persistent threat, ransomware, phishing emails, cryptojacking, financial threats, to fileless attacks. However, since the PowerShell language is dynamic by design and can construct script pieces at different levels, state-of-the-art static analysis based PowerShell attack detection approaches are inherently vulnerable to obfuscations. To overcome this challenge , in this paper we design the first effective and lightweight deobfuscation approach for PowerShell scripts. To address the challenge in precisely identifying the recoverable script pieces, we design a novel subtree-based deobfuscation method that performs obfuscation detection and emulation-based recovery at the level of subtrees in the abstract syntax tree of PowerShell scripts. Building upon the new deobfuscation method, we are able to further design the first semantic-aware PowerShell attack detection system. To enable semantic-based detection, we leverage the classic objective-oriented association mining algorithm and newly identify 31 semantic signatures for PowerShell attacks. We perform an evaluation on a collection of 2342 benign samples and 4141 malicious samples, and find that our deobfuscation method takes less than 0.5 seconds on average and meanwhile increases the similarity between the obfuscated and original scripts from only 0.5% to around 80%, which is thus both effective and lightweight. In addition, with our deobfuscation applied, the attack detection rates for Windows Defender and VirusTotal increase substantially from 0.3% and 2.65% to 75.0% and 90.0%, respectively. Furthermore, when our deobfuscation is applied, our semantic-aware attack detection system outperforms both Windows Defender and VirusTotal with a 92.3% true positive rate and a 0% false positive rate on average


近年来，越来越多的报道显示，PowerShell被广泛的用于各种网络攻击。这些攻击包括高级持续性威胁、勒索病毒、网络钓鱼邮件等等。基于PowerShell的攻击，利用了PowerShell的动态性，构造了复杂的混淆模式，绕过了检测。为了克服这一难题，我们提出来第一个轻量且有效的解混淆方案，并基于解混淆后的脚本构造了基于攻击语义的检测系统。实验显示，通过解混淆，我们可以将混淆后脚本和原始脚本之间的相似度从仅0.5％提高到了近80％。同时解混淆过程有效的改善了已有系统的检测效率，Windows Defender和VirusTotal的攻击检测率分别从0.3％和2.65％大幅增加到75.0％和90.0％。利用我们提取的31条语义签名，检测率最高可达到92.3%。

## System Overview
![An overview of the proposed subtree-based deobfuscation for PowerShell scripts.](https://github.com/li-zhenyuan/PowerShellDeobfuscation/raw/master/Images/SystemStructure.png)
