The Social Life of Industrial Arms: How Arousal and Attention Shape Human-Robot Interaction

Roy El-Helou1 and Matthew K.X.J. Pan1

Abstract— This study explores how human perceptions of a This work explores a fundamental question: Why and how non-anthropomorphic robotic manipulator can be shaped by should robots be designed with character-like qualities? We two key dimensions of behaviour: arousal, defined as the robot’s are particularly interested in how robots can use behavioural movement energy and expressiveness, and attention, defined as the robot’s capacity to selectively orient toward and engage cues—such as movement, posture, and attention—to project with a user. We present an integrated behaviour system that emotional and social presence, even without anthropomor-applies and extends existing movement-centric design princi-phic features. By endowing robots with the ability to exhibit ples to non-anthropomorphic robots. Our system combines a emotionally expressive behaviour, we aim to deepen human-gaze-like attention engine with an arousal-modulated motion machine interaction and improve the quality of user expe-layer to explore how expressive and interactive behaviours influence social perception in robotic manipulators. In a user rience. In such an endeavour, it is essential to consider not study, we find that robots exhibiting high attention—actively only the capability of robots to communicate emotions but directing their focus toward users—are perceived as warmer also how humans perceive these expressions. For instance, and more competent, intentional, and lifelike. In contrast, the findings from \[2\] suggest that adaptive emotional robots high arousal—characterized by fast, expansive, and energetic can foster rapport and immediacy in educational settings, motions—increases perceptions of discomfort and disturbance. 

Importantly, a combination of focused attention and moderate thus leading to improved learning outcomes. Furthermore, arousal yields the highest ratings of trust and sociability, according to \[3\], establishing emotional bonds and providing while excessive arousal diminishes social engagement. These consistent support are key aspects of long-term human-robot findings offer design insights for endowing non-humanoid robots relationships, which can be applied to addressing social with expressive, intuitive behaviours that support more natural isolation and similar challenges. 

human-robot interaction. 

In this work, we focus on non-anthropomorphic robots I. INTRODUCTION

\(NARs\) —specifically, robotic manipulators—and examine how they can express emotional character through two key As robots become increasingly integrated into human behavioural dimensions: arousal, defined as the robot’s level environments—from homes and classrooms to healthcare of energy or movement intensity, and attention, defined and industrial settings—designing them to interact naturally as its capacity to selectively orient its “gaze” toward and and intuitively with people is becoming a central challenge engage with human users. Both dimensions are demonstrated in human-robot interaction \(HRI\). While much of robotics in Fig. 1. Our proposed system architecture integrates an has focused on functional performance, there is growing arousal-modulated motion model, inspired by prior work on recognition that social and emotional capabilities are equally expressive movement in robotics, \[4\], \[5\], with an interactive crucial for fostering trust, collaboration, and engagement \[1\]. 

focus mechanism we call the attention engine. To evaluate this architecture, we conduct a user study examining how 1Roy El-Helou and Matthew Pan are with the Ingenuity Labs Re-variations in arousal and attention affect human perceptions search Institute and the Department of Electrical and Computer Engineer-ing, Queen’s University, Kingston, Canada \(e-mails: 19reh2@queensu.ca, of the robot’s warmth, competence, animacy, and social matthew.pan@queensu.ca\). 

intentionality. The results offer insights into how expressive Fig. 1. 

Photos showing varying robot poses as a result of varying the arousal level of the proposed architecture controlling the emotional and social behaviours of a Universal Robots UR5e manipulator. 

motion and attentional behaviours can enhance the social or calm responses \[21\], \[16\]. Unlike valence, as defined presence of NARs. 

by Russell in \[22\], which relies on affective expressions difficult to convey without anthropomorphic features, arousal II. RELATED WORK

is inherently expressible through kinematics alone. 

Traditionally, the ability to convey emotions has been re-Gaze-based attention was selected for its critical role in served for more anthropomorphic robots –machines designed engagement and social presence. A robot’s ability to direct with human-like features that naturally lend themselves to the its gaze or orient toward users conveys intentionality and expression of human emotions \[6\]. Anthropomorphic robots responsiveness, shaping perceptions of agency, sociability, have been widely studied in social human-robot interaction and competence \[11\], \[12\], \[23\]. In non-humanoid robots, \(HRI\), particularly for their ability to use both verbal and attention can be approximated through gaze-like behaviours non-verbal communication modes like kinesics, proxemics, embedded in motion, allowing the system to remain expres-haptics, and voice modulation \[7\]–\[9\]. Studies on such robots sive despite lacking eyes or a face. 

emphasize that nonverbal behaviours, including gestures and These two dimensions offer complementary yet distinct postures, can shift human cognitive framing, elicit emotional ways for robotic arms to communicate internal state and responses, and improve task performance \[10\]. Furthermore, interpersonal awareness. We now describe the architecture eye gaze plays a critical role in human-robot communica-developed to implement and evaluate these behaviours in a tion, irrespective of the robot’s form. It has been shown to robotic manipulator. 

direct user attention, regulate conversational flow, and convey engagement or intent. Eye gaze has been used in multi-IV. CONTRIBUTIONS

modal interaction to combine attention-directing cues with We present a system that integrates and adapts known other communication modes, improving the robot’s ability design principles, such as arousal-modulated motion and to integrate into human environments \[11\], \[12\]. However, interactive attention for non-anthropomorphic robots \[4\], anthropomorphic robots also face social hurdles, such as the

\[19\]. While the components of this system are grounded in uncanny valley, a phenomenon in which a certain level of prior work \[18\], \[5\], \[20\], our contribution lies in combining human likeness elicits feelings of discomfort \[13\]. 

them within a unified framework but also in documenting Instead, our work explores using NARs to behave socially the implementation and parameterization that enable these and emotionally. NARs, such as robotic manipulators, lack behaviours to run in real time on a non-anthropomorphic human-like attributes, which makes the task of emotional ex-manipulator, and in evaluating their social and emotional pression different and more challenging. NARs often appear impact in a user study. Our contributions are as follows: mechanical and devoid of personal content, lacking the emo-

• We design an expressive control system that integrates tional depth observed in their anthropomorphic counterparts arousal-based motion modulation with a real-time atten-

\[14\]. However, prior work on social and emotional content tion engine in a robotic manipulator with natural motion designed for NARs discusses how postural adjustments in continuity in mind. 

robots can shift emotional framing and trigger specific human

• We conduct a factorial user study that evaluates how responses \[15\]–\[17\]. Recent work has shown that expressive attention and arousal jointly shape perceptions of dis-movement can significantly improve robot readability and comfort and sociability in NARs. 

engagement; studies incorporating animation principles, such

• We provide empirical insights into the social dynamics as anticipation and reaction, demonstrate that motion design of expressive motion in non-humanoid robots, support-influences how users perceive a robot’s competence and ing their use in socially embedded contexts. 

intelligence \[18\]. Additionally, a movement-centric approach These contributions are framed around the following research suggests that robot motion should be designed as a primary questions:

communication channel rather than an auxiliary feature \[19\]. 

Beyond animation-driven readability, the interplay between 1\) How can NARs convey emotional character through expressive and functional movement has been studied in movement and interactivity without relying on anthro-NARs. The ELEGNT framework proposes that robots should pomorphic features? 

integrate both function-driven and expression-driven move-2\) What are the key factors in robotic movement and ments to enhance user engagement and communication, even behaviours that can be optimized to evoke specific in robots designed primarily for task execution \[20\]. This emotional responses from humans and enhance their work aligns with research showing that expressive motion emotional engagement? 

helps users anticipate robot actions and infer internal states, 3\) How do varying levels of arousal and attention influ-making interactions more intuitive. 

ence human perceptions of a robot’s social presence and intentionality? 

III. MOTIVATIONS

With these contributions in mind, we next describe the While prior work has examined expressive motion and system architecture developed to explore how arousal and social signalling in robots \[21\], \[19\], \[18\], few studies have attention shape human perceptions of NARs. This framework integrated these behaviours into a unified framework for provides the basis for answering our research questions robotic manipulators. Our work builds on this movement-through controlled behavioural modulation and interactive centric perspective and focuses specifically on two core experimentation. 

behavioural dimensions: arousal and attention. 

We chose arousal, defined as movement energy or inten-V. SYSTEM DESIGN

sity, because it maps directly to robot motion, making it Our behaviour generation system integrates attention and particularly well-suited for non-anthropomorphic platforms arousal mechanisms to support expressive and socially re-that lack facial or vocal expressivity. High arousal behaviours, sponsive interaction in robotic manipulators. It enables the such as fast, expansive motion, can convey urgency or robot to dynamically orient to human presence while mod-excitement, while low arousal produces subdued, hesitant, ulating its energy and motion profile to convey emotional



where wp and wv represent the weight for the position and velocity components of an individual such as their torso and hands in the environment, respectively. The weights are chosen based on their relative importance and influence on attention. Θ\(t\) is a habituation factor, described in further detail below. The position score P combines proximity and hand position factors:

P = wproximityeλd \+ whand\(hleft \+ hright\) \(2\)

where d is the Euclidean distance to the individual, λ is a decay constant, and hleft, hright are binary indicators of whether either hand is raised above shoulder level. This formulation prioritizes nearby individuals and interprets raised hands as social gestures, such as waving. λ is used to modulate the influence of distance on the attention score, ensuring that closer individuals are prioritized, similarly to natural human tendency. 

The velocity score V captures torso and hand motion, normalized by maximum observed velocities: vtorso

vright

vleft

V =

\+

\+

\(3\)

vmax torso

vmax right

vmax left

Thus, the faster an individual moves, the more salient \(i.e., having a larger attention score\) the individual becomes; normalization ensures responsiveness across varying activity levels. 

To avoid sustained attention on a single user, we apply a habituation factor Θ\(t\) that dynamically adjusts based on Fig. 2. 

System architecture diagram for our proposed interactive and expressive robot behaviour system. 

gaze history:

Θ\(t\) = Θ\(t − 1\) \+ \(γm

character. As shown in Fig. 2, the system consists of two hab \+ \(1 − γ\)mrest\)∆t

\(4\)

main components: an attention engine, which determines Here, γ = 1 for the currently attended individual and 0 for which stimuli the robot should attend to \(Section V-A\), and others; mhab and mrest control the negative decay and positive a gaze-tracking algorithm \(Section V-B\). We implemented recovery rates respectively, and ∆t is the time step. Which this system on a Universal Robots UR5e manipulator \[24\], provides a natural decay in attention for sustained interactions illustrated in Fig. 1, and evaluated it through a user study while allowing recovery during periods of disengagement. 

examining human perceptions of the robot \(Section VI\). 

Θ\(t\) is bounded between 0 and 1 to maintain naturalistic attention shifts and prevent fixation. 

A. Attention Engine

As its name suggests, the attention engine is the component B. Robotic Gaze Algorithm

in our system which directs the robot’s attention to salient The gaze algorithm maps 3D target positions to joint-space features/stimuli in its visual environment; in our case these postures, enabling the robot to orient toward salient individ-stimuli are users and individuals within range of a RGB-D

uals. Though implemented on a UR5e arm, the approach is sensor \(Intel RealSense D435 Depth Camera\) affixed in front generalizable to any articulated platform. It prioritizes distal of the robot \[25\]. It builds on an approach introduced by joints to produce localized gaze-like motion without requiring Pan et al. \[5\], that was utilized for a humanoid animatronic full-body movement. Arousal modulates posture and motion bust and governs the robot’s decision-making by computing dynamics: low arousal produces subdued, minimal motion; an attention score for each detected individual, determining high arousal increases speed, amplitude, and reach. This saliency and guiding the robot’s gaze to enable dynamic, variation creates visible difference in energy and expressive-responsive interactions. 

ness aligned with emotional intent. To enhance realism, a Each attention score is a weighted combination of posi-sinusoidal oscillation is applied to joint angles to simulate tional cues, movement dynamics, and a habituation factor breathing. Oscillation intensity scales with arousal, adding that prevents prolonged fixation on a single target—reflecting subtle motion that avoids stillness and improves lifelikeness. 

how humans distribute attention across multiple people and When secondary cues, such as raised hands, are detected, the stimuli. The factors and weights of the score were developed robot briefly shifts gaze before returning to the primary target, through trial and error testing and subjective feedback from reinforcing a sense of reactivity. In idle states, it orients participants of what the robot should do when presented with toward a virtual target within reach, maintaining continuity in different stimuli. 

motion even without human input. The result is a platform-The score Φ is defined as:

agnostic system for generating socially meaningful gaze using arm motion, modulated by internal state and real-time Φ = wpP \+ wvV \+ Θ\(t\)

\(1\)

cues from the environment. 

C. Attentional Drift Module with the order counterbalanced using a Latin square to control Early pilot studies revealed that continuous fixation on a for carryover effects. 

user often felt repetitive or overly mechanical, an observation Participants were instructed to engage with the robot freely, supported by prior findings showing that excessive gaze without a specific task or time limit, and to avoid entering persistence can reduce perceived naturalness and engagement the robot’s workspace. This open-ended format was chosen in social robots

\[26\]. To address this, we introduce an to encourage spontaneous behaviour and allow natural social Attentional Drift Module that injects naturalistic variability interpretations of the robot’s actions. While this approach into the robot’s gaze behaviour. Inspired by patterns of avoids task-driven bias and supports explorations of per-spontaneous attentional shifts in humans

\[27\], the mod-

ceived social intent, it introduces variability in interaction ule generates transient virtual targets within the robot’s style and duration across participants. Future comparisons workspace. These targets are instantiated probabilistically, with goal-directed tasks could help contextualize these re-with their likelihood increasing alongside the robot’s arousal sponses. 

level. Each target is assigned a randomized position and brief After each session, participants completed a combined lifespan, temporarily overriding the robot’s primary gaze and post-condition survey \(Robotic Social Attributes Scale and prompting a brief redirection before fading. The drift module Human-Robot Interaction Evaluation Scale\) \[29\], \[30\] mea-is a process embedded within the robot control loop so that suring perceptions of warmth, competence, sociability, ani-momentary attentional shifts are produced without disrupting macy, intentionality, discomfort, and disturbance. Participants motion continuity. This allows the robot to avoid mechanical rated each item on the inventories on scales of one to seven stiffness, to maintain expressive continuity and help foster a where one represents strongly disagree and seven represents more lifelike presence. 

strongly agree. Interactions were audio/video recorded for later analysis, though data from two participants were ex-VI. USER STUDY

cluded due to lack of consent or technical error. 

To evaluate the effectiveness of the proposed behaviour generation system, we conducted a user study investigating VII. RESULTS

how variations in arousal and attention influence human perceptions of a non-anthropomorphic robot. Building on the A total of 36 participants were recruited to participate system described in Section V, this study examines the social without compensation through on- and off-campus advertis-and emotional impact of robot behaviour through open-ended ing. The sample included 18 males and 18 females \(none human-robot interactions and was approved by the Queen’s identified as non-binary, transgender, or other gender iden-University General Research Ethics Board \(GELEC-139-22, tities\), with ages ranging from 18 to 25 years \(M = 21.7, File No. 6036728\). 

SD = 1.58\). 

We specifically explore two behavioural dimensions: arousal, operationalized as the robot’s movement energy, and A. Baseline Attitudes

attention, defined as the robot’s capacity to direct gaze and responsiveness toward users. These factors were selected due Pre-study attitudes, as measured by the GAToRS sur-to their central role in shaping user perceptions of social vey \[28\], revealed generally positive perception ratings \(out agents, as discussed in Section II. A 2 × 2 factorial design of 7\) of robots. On the personal level, participants reported was employed, crossing two levels of arousal \(low and high\) moderate comfort and enjoyment around robots \(P \+ = 4.44, with two levels of attention \(low and high\), resulting in four SD = 1.52\) and low levels of unease \(P − = 2.93, SD =

experimental conditions. 

1.67\). On the societal level, participants expressed optimism about the impact of robots \(S\+ = 5.92, SD = 1.05\), though A. Conditions

concerns about potential risks remained present \(S− = 5.11, 

• Low Attention: The robot remains in an idle state and SD = 1.60\), with more variability in responses. 

does not track or respond to human users. It intermit-tently shifts its gaze toward virtual stimuli generated by B. Main Effects and Interaction Analysis the virtual object manager. 

A 2 × 2 within-subjects repeated-measures ANOVA re-

• High Attention: The robot actively tracks and responds vealed several significant main effects of attention. Attention to the participant with gaze and posture adjustments, significantly influenced warmth, F \(1, 35\) = 16.97, p < .001, following the mechanisms described in Sections V-A η2 = .327; competence, F \(1, 35\) = 175.35, p < .001, and V-B. 

η2 = .834; sociability, F \(1, 35\) = 7.22, p < .01, η2 = .171; 

• Low Arousal: Arousal is set to its minimum value animacy, F \(1, 35\) = 18.05, p < .001, η2 = .340; and \(1\), resulting in slow, conservative motion, a hunched intentionality, F \(1, 35\) = 65.32, p < .001, η2 = .651. 

posture, and limited range of movement to create a subdued and deliberate behavioural profile. 

Arousal also produced significant effects, increasing discomfort, F \(1, 35\) = 10.70, p < .01, η2 = .234; decreasing

• High Arousal: Arousal is set to its maximum value \(10\), producing faster, more dynamic movement with sociability, F \(1, 35\) = 4.75, p < .05, η2 = .120; and an upright posture and extended reach, conveying a increasing disturbance, F \(1, 35\) = 7.58, p < .01, η2 = .178. 

heightened energy level. 

In addition, there were significant Arousal × Attention interaction effects for discomfort, F \(1, 35\) = 4.64, p < .05, B. Protocol

η2 = .117, and sociability, F \(1, 35\) = 5.38, p < .05, The study was conducted in a controlled lab environment. 

η2 = .133, indicating that the influence of arousal on these Participants first completed a pre-study survey \(General measures depended on the level of attention. 

Attitudes Towards Robots Scale\) \[28\] assessing baseline These omnibus effects were followed up with Bonferroni-attitudes towards robots. Each participant then experienced corrected pairwise comparisons to examine the specific dif-four interactions sessions, one per experimental condition, ferences between conditions. 



C. Post Hoc Comparisons

• Low Arousal, Low Attention: M = 75.70, SD = 33.51

Bonferroni-corrected pairwise comparisons revealed the

• Low Arousal, High Attention: M = 68.20, SD = 32.23

following effects ratings out of seven:

• High Arousal, Low Attention: M = 62.97, SD = 26.50

• High Arousal, High Attention: M = 61.44, SD =

• Disturbance: Higher in high \(M = 3.87, SD = 0.24\) 38.34

vs. low arousal \(M = 3.34, SD = 0.22\), p < .01. 

• Warmth: Higher in high \(M = 3.77, SD = 0.17\) vs. 

Arousal level had a significant effect on interaction dura-low attention \(M = 3.01, SD = 0.15\), p < .001. 

tion \(F = 4.66, p < .05, η2 = .124\), with longer interactions

• Competence: Higher in high \(M = 5.11, SD = 0.11\) observed in low arousal conditions \(M = 71.96, SD = 4.83\) vs. low attention \(M = 3.06, SD = 0.17\), p < .001. 

than in high arousal conditions \(M = 62.21, SD = 4.99\). 

• Animacy: Higher in high \(M = 4.10, SD = 0.17\) vs. 

low attention \(M = 3.44, SD = 0.19\), p < .001. 

VIII. DISCUSSION

• Intentionality: Higher in high \(M = 4.95, SD = 0.13\) While this study yielded a broad set of findings, we focus vs. low attention \(M = 3.53, SD = 0.16\), p < .001. 

here on the three research questions posed earlier: \(1\) how Interaction Effects: Significant interaction effects are vi-can NARs convey emotional character through movement, sualized in Fig. 3. In high attention conditions, discomfort \(2\) which parameters most influence perceptions of emotional ratings were significantly higher in high arousal \(M = 3.71, and social engagement, and \(3\) how do arousal and attention SD = 0.27\) than low arousal \(M = 2.79, SD = 0.20\), interact to shape impressions of a robot’s presence and p < .01. Furthermore, in high attention conditions, sociability intent. We structure this discussion around three key themes: ratings were significantly lower in high arousal \(M = 3.31, expressive attention, arousal and discomfort, and behavioural SD = 0.27\) than low arousal \(M = 4.17, SD = 0.21\), balance. 

p < .01. 

Attention had the most consistent and positive effect on perceived intentionality, warmth, and competence. Even with-TABLE I

out anthropomorphic features, dynamic orientation toward SIGNIFICANT RESULTS FOR AROUSAL AND ATTENTION EFFECTS

the user appeared sufficient to suggest social awareness and intent. This aligns with prior work showing that gaze-like Source

Measure

F

Partial η2

Power

behaviour can elicit engagement and perceptions of agency, Discomfort

10.703\*\*

.234

.889

even in non-humanoid systems \[23\], \[12\]. Participants ap-Arousal

Sociability

4.753\*

.120

.564

Disturbance

7.578\*\*

.178

.763

peared to interpret attentional cues as responsive and delib-Warmth

16.971\*\*\*

.327

.980

erate rather than purely mechanical. This supports existing Competence

175.349\*\*\*

.834

1.000

theories of joint attention as a potent expressive tool, even Attention

Sociability

7.217\*\*

.171

.743

in minimal or industrial robot designs. For NARs, dynamic Animacy

18.051\*\*\*

.340

.985

Intentionality

65.315\*\*\*

.651

1.000

orientation may offer a viable alternative to anthropomorphic expressivity, conveying presence without relying on form. 

Discomfort

4.637\*

.117

.553

Arousal × Attention

Sociability

5.376\*

.133

.616

In contrast, arousal broadly had negative effects on social

\*p < .05, \*\*p < .01, \*\*\*p < .001

perception. As arousal increased, participants reported higher levels of discomfort and disturbance, and rated the robot as less sociable. These findings challenge the assumption that increased energy contributes positively to perceived engagement. Instead, excessive motion speed or amplitude may signal volatility, unpredictability, or threat. Prior work shows that motion legibility improves trust when movements are predictable and well-scaled to context. In our study, the high-arousal conditions may have violated those expectations, especially in a form factor typically associated with precision and stability. Without anthropomorphic cues to contextualize high-energy behaviour, users may default to interpreting it as chaotic or unsafe. For NARs, this places an upper bound on expressivity through arousal alone: too much motion energy can erode social comfort, even when paired with high attention. 

The most socially successful behaviours emerged when attention was high and arousal remained low. This pairing was consistently rated as the most sociable, least disturbing, and among the most competent. Users appear to prefer systems that are attentive without being overstimulating. This reflects broader human norms around affect regulation, where calm focus is associated with trustworthiness and emotional control. These findings reinforce principles from frameworks Fig. 3. 

Interaction effect of arousal and attention on discomfort and sociability ratings. 

like ELEGNT \[20\], which argue that expressive movement should enhance rather than distract from the interaction. 

For NARs, behaviour must strike a balance between clarity D. Interaction Time

and intensity. Our results suggest that subtlety, rather than Interaction duration \(in seconds\) for each trial was also raw energy, is key to sustaining positive social dynamics in analyzed. Average times by condition were: robotic arms. 

While this study offers valuable insights into expressive

\[7\] P. Chevalier, J. J. Li, E. Ainger, A. M. Alcorn, S. Babovic, V. Charisi, behaviour design for NARs, several limitations warrant conS. Petrovic, B. R. Schadenberg, E. Pellicano, and V. Evers, “Dialogue Design for a Robot-Based Face-Mirroring Game to Engage Autistic sideration. First, interactions were short-term and took place Children with Emotional Expressions,” in Social Robotics, A. Kheddar, in a controlled laboratory setting with a relatively homoge-E. Yoshida, S. S. Ge, K. Suzuki, J.-J. Cabibihan, F. Eyssel, and H. He, neous participant pool, that is university students aged 18

Eds. 

Cham: Springer Int. Publ., 2017, pp. 546–555. 

\[8\] Y. Kim and B. Mutlu, “How social distance shapes human–robot to 25. These constraints limit the ecological validity and interaction,” Int. J. Hum.-Comput. Stud., vol. 72, no. 12, pp. 783–795, generalizability of our findings to more diverse and real-Dec. 2014. 

world contexts. Second, the interactions were intentionally

\[9\] H. N. Green, M. M. Islam, S. Ali, and T. Iqbal, “Who’s Laughing NAO? Examining Perceptions of Failure in a Humorous Robot Part-open-ended and task-free to encourage spontaneous social ner,” in Proc. 2022 ACM/IEEE Int. Conf. Hum.-Robot Interact., ser. 

interpretations and reduce task-induced bias. However, we HRI ’22. 

Sapporo, Hokkaido, Japan: IEEE Press, Mar. 2022, pp. 

recognize that task context likely shapes how users perceive 313–322. 

\[10\] S. Saunderson and G. Nejat, “How robots influence humans: A survey arousal and attention. Third, we employed a fixed, linear of nonverbal communication in social human–robot interaction,” Int. 

arousal parameter to enable clear experimental control. While J. Social Robotics, vol. 11, no. 4, pp. 575–608, 2019. 

this simplification facilitated isolating the effects of arousal, 

\[11\] C. Stanton and C. Joanna Stevens, “Robot Pressure: The Impact of Robot Eye Gaze and Lifelike Bodily Movements upon Decision-it lacks adaptability. Future research could explore dynamic Making and Trust,” 6th Int. Conf. Social Robotics ICSR, Oct. 2014. 

arousal models, such as bio-inspired or homeostatic frame-

\[12\] A. J. Moon, D. M. Troniak, B. Gleeson, M. K. Pan, M. Zheng, B. A. 

works that better reflect contextual or user-driven changes. 

Blumer, K. MacLean, and E. A. Croft, “Meet Me where I’m Gazing: How Shared Attention Gaze Affects Human-Robot Handover Timing,” 

Beyond the lab setting, the same attention-arousal mecha-in 2014 9th ACM/IEEE Int. Conf. Hum.-Robot Interact. \(HRI\), Mar. 

nisms could support scenarios such as collaborative work, 2014, pp. 334–341, iSSN: 2167-2121. 

assistive service, or public interaction, where smooth expres-

\[13\] M. Mori, K. F. MacDorman, and N. Kageki, “The Uncanny Valley

\[From the Field\],” IEEE Robot. Autom. Mag., vol. 19, no. 2, pp. 98–

sive cues help a robot signal readiness, intent, or engagement. 

100, Jun. 2012. 

We leave these contexts open for future exploration. 

\[14\] L. H. Kim, V. Domova, Y. Yao, C.-M. Huang, S. Follmer, and P. E. 

Paredes, “Robotic Presence: The Effects of Anthropomorphism and IX. CONCLUSION

Robot State on Task Performance and Emotion,” IEEE Robot. Autom. 

Lett., vol. 7, no. 3, pp. 7399–7406, Jul. 2022. 

This work presents a behaviour generation system for

\[15\] A. E. Scheflen, “The significance of posture in communication sys-NARs that leverages arousal and attention to support tems,” Psychiatry, vol. 27, pp. 316–331, Nov. 1964. 

emotionally expressive and socially engaging interactions. 

\[16\] M. S. Erden, “Emotional Postures for the Humanoid-Robot Nao,” Int. 

J. Social Robotics, vol. 5, no. 4, pp. 441–456, Nov. 2013. 

Through a controlled user study, we examined how variations

\[17\] M. Zecca, Y. Mizoguchi, K. Endo, F. Iida, Y. Kawabata, N. Endo, in these two dimensions influence human impressions of a K. Itoh, and A. Takanishi, “Whole body emotion expressions for robotic manipulator. Our findings show that high attention KOBIAN humanoid robot — preliminary experiments with different Emotional patterns —,” in RO-MAN 2009 - 18th IEEE Int. Symp. Robot significantly enhances perceptions of warmth, competence, Hum. Interact. Commun., Sep. 2009, pp. 381–386, iSSN: 1944-9437. 

intentionality, and animacy, while high arousal—expressed

\[18\] L. Takayama, D. Dooley, and W. Ju, “Expressing thought: Improving through fast and expansive motion—can increase discomfort robot readability with animation principles,” in 2011 6th ACM/IEEE

Int. Conf. Hum.-Robot Interact. \(HRI\), Mar. 2011, pp. 69–76, iSSN: and disturbance. These results underscore the importance 2167-2148. 

of balancing energy and engagement: attentional cues are

\[19\] G. Hoffman and W. Ju, “Designing robots with movement in mind,” 

effective in eliciting positive social responses, but excessive J. Hum.-Robot Interact., vol. 3, no. 1, pp. 91–122, Feb. 2014. 

\[20\] Y. Hu, P. Huang, M. Sivapurapu, and J. Zhang, “ELEGNT: Expressive arousal may diminish the robot’s social acceptability. 

and Functional Movement Design for Non-anthropomorphic Robot,” 

The study demonstrates that even robots without human-Jan. 2025, arXiv:2501.12493 \[cs\]. 

like features can convey character-like behaviour when de-

\[21\] C. Breazeal, “Emotion and sociable humanoid robots,” Int. J. Hum.-

Comput. Stud., vol. 59, no. 1, pp. 119–155, Jul. 2003. 

signed with appropriate expressive strategies. These insights

\[22\] J. A. Russell, “A Circumplex Model of Affect,” Journal of Personality offer concrete guidance for the design of socially intuitive and Social Psychology, Dec. 1980. 

robotic systems, particularly in non-humanoid forms. While

\[23\] H. Admoni and B. Scassellati, “Social Eye Gaze in Human-Robot Interaction: A Review,” J. Hum.-Robot Interact., vol. 6, no. 1, p. 25, our findings are limited by factors such as the short-term Mar. 2017. 

nature of the interactions and scope, this work lays the

\[24\] “UR5e

Lightweight, 

versatile

cobot.” 

\[Online\]. 

Available:

groundwork for future studies on long-term engagement, https://www.universal-robots.com/products/ur5-robot/

\[25\] “Intel® RealSense™ Depth Camera D435 - Product Specifications.” 

adaptive behaviours, and deployment in diverse real-world

\[26\] J. Park, T. Jeong, H. Kim, T. Byun, S. Shin, K. Choi, J. Kwon, T. Lee, contexts. 

M. Pan, and S. Choi, “Towards Embedding Dynamic Personas in Interactive Robots: Masquerading Animated Social Kinematic \(MASK\),” 

REFERENCES

IEEE Robot. Autom. Lett., vol. 9, no. 10, pp. 8826–8833, Oct. 2024. 

\[27\] M. Dalmaso, L. Castelli, and G. Galfano, “Social modulators of gaze-

\[1\] T. Law, M. Chita-Tegmark, and M. Scheutz, “The Interplay Between mediated orienting of attention: A review,” Psychon. Bull. Rev., vol. 27, Emotional Intelligence, Trust, and Gender in Human–Robot Interac-no. 5, pp. 833–855, Oct. 2020. 

tion,” Int. J. Social Robotics, vol. 13, no. 2, pp. 297–309, Apr. 2021. 

\[28\] M. Koverola, A. Kunnari, J. Sundvall, and M. Laakasuo, “General

\[2\] K. Y. Fung, L. H. Lee, K. F. Sin, S. Song, and H. Qu, “Humanoid robot-Attitudes Towards Robots Scale \(GAToRS\): A new instrument for empowered language learning based on self-determination theory,” 

social surveys,” Int. J. Social Robotics, vol. 14, no. 7, pp. 1559–1581, Education and Information Technologies, vol. 29, no. 14, pp. 18 927–

2022. 

18 957, 2024. 

\[29\] C. M. Carpinella, A. B. Wyman, M. A. Perez, and S. J. Stroessner, 

\[3\] O. E. Lee, H. Lee, A. Park, and N. G. Choi, “My precious friend:

“The Robotic Social Attributes Scale \(RoSAS\): Development and Human-robot interactions in home care for socially isolated older Validation,” in 2017 12th ACM/IEEE Int. Conf. Hum.-Robot Interact. 

adults,” Clinical Gerontologist, vol. 47, no. 1, pp. 161–170, 2024. 

\(HRI\), Mar. 2017, pp. 254–262, iSSN: 2167-2148. 

\[4\] G. Venture and D. Kulić, “Robot Expressive Motions: A Survey of

\[30\] N. Spatola, B. Kuhnlenz, and G. Cheng, “Perception and Evaluation in Generation and Evaluation Methods,” J. Hum.-Robot Interact., vol. 8, Human–Robot Interaction: The Human–Robot Interaction Evaluation no. 4, pp. 20:1–20:17, Nov. 2019. 

Scale \(HRIES\)—A Multicomponent Approach of Anthropomorphism,” 

\[5\] M. K. Pan, S. Choi, J. Kennedy, K. McIntosh, D. C. Zamora, in Int. J. Social Robotics, vol. 13, Jan. 2021, pp. 1517–1539. 

G. Niemeyer, J. Kim, A. Wieland, and D. Christensen, “Realistic and Interactive Robot Gaze,” in 2020 IEEE/RSJ Int. Conf. Intell. Robots Syst. \(IROS\), Oct. 2020, pp. 11 072–11 078, iSSN: 2153-0866. 

\[6\] N. Spatola and O. A. Wudarczyk, “Ascribing emotions to robots: Explicit and implicit attribution of emotions and perceived robot anthropomorphism,” Comput. Hum. Behav., vol. 124, p. 106934, Nov. 

2021.



