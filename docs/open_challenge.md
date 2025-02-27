# An AI-based Game Evaluator

## Hiring Notification
- This project is now open to **interns** or **part-time** contributors. If you are interested in this AI application project or have a passion for the AI and gaming field, feel free to contact us.
- **Email**: pengxzh@rpggo.ai

## 1. Project Background

The website rpggo.ai hosts a diverse array of text-based RPG games, all created by gaming enthusiasts. These games can be experienced using our proprietary game engine, the Zagii-Engine. This platform aims to bring a community-driven gaming experience by allowing users to craft and share their adventures.

Try it out here 👉: https://rpggo.ai

![image](https://github.com/RPGGO-AI/oasis/blob/main/docs/images/game_lobby.png)


**We are looking to** develop an AI-based Game Evaluator with the primary objectives of:
- Creating an automated evaluation tool to ensure quality and consistency when the Zagii-Engine undergoes upgrades.
- Performing routine evaluations of games on the website to identify exceptional or underwhelming games, thus aiding operational staff in their development follow-ups, and potentially facilitating the creation of an AI-driven recommendation list.

The benefits of the AI Game Evaluator extend beyond these objectives, including:
- The potential for the AI Game Evaluator to evolve into a game player's assistant or copilot, helping players to better navigate and explore games.
- Serving as a rapid testing tool for creators during the Game Creation phase, providing quick evaluation results or further modification suggestions, potentially forming an essential foundation for a Creator Copilot.


## 2. Project Requirements

The AI Game Evaluator should be capable of assessing any game on rpggo and providing optimization suggestions.

### We provide the following API interface:
- An API interface to retrieve essential game information, aiding the evaluator in understanding the game's foundational setup.
  - This interface can access all the information visible to a game player, as illustrated in the image below:
    ![image](https://github.com/RPGGO-AI/oasis/blob/main/docs/images/game_meta.PNG)
- A Game Management API interface
  - Provides functions such as starting a game or switching chapters to control game progression.
- A Game Dialogue API interface
  - Serves as an API allowing players to converse with any NPC within the game, enabling the Game Evaluator to simulate a player's gameplay experience.
  - This interface also provides notifications for any changes in the game state.

**Detailed API information**: https://developer.rpggo.ai/dev-docs/player-api/api-overview/api-v2-new

### Required Implementation:
- Develop an AI-based Game Player that interacts with NPCs according to the game settings and rules for several rounds, resulting in a comprehensive game interaction session.
- Utilize AI models to automatically evaluate this interaction session, rate the gaming experience, and highlight the game's strengths and areas for improvement.


## 3. An Open Source Implementation Plan
We offer an initial implementation plan, which may serve as an example or a baseline.

### System Framework Diagram
Here is a high-level overview of the system framework:
![image](https://github.com/RPGGO-AI/oasis/blob/main/docs/images/ai_evaluator.png)

### Code Repository
GitHub: https://github.com/RPGGO-AI/oasis


## 4. About Game Evaluation

### Evaluation Modes
We aim to support the following two evaluation modes:
- Player Perspective Evaluation
  - Evaluating the game from a player's viewpoint by playing several rounds, then providing feedback and improvement suggestions. This assists creators in optimizing their game works more efficiently.

- Model Comparison Evaluation
  - Using different dialogue models and request parameters under the same game setting to compare performance. This assists developers in assessing the impact of technical iterations.

### Evaluation Criteria

- Game Aspects
  - Focus on aspects such as:
    - Playability of the game
    - Richness of the storyline
    - Style & theme
    - ......

- NPC Characteristics
  - Focus on aspects such as:
    - Whether NPCs adhere to character settings in their role-playing
    - The impact of NPCs on advancing the game’s storyline
    - Whether NPC dialogues are cohesive and free from inappropriate language usage, repetition, etc.
    - ......

### Examples

#### A gameplay session
```json
"gameplay_session_1": [
    {
        "name": "Tyrion Lannister",
        "content": "Ah, a new face! Shall we drink and exchange wits?"
    },
    {
        "name": "Player",
        "content": "I'm Jon Snow, king now. Join me as Hand?"
    },
    {
        "name": "Tyrion Lannister",
        "content": "Ah, King Jon Snow. A bastard turned monarch—how poetic! Fine, I’ll be your Hand. But don’t expect me to lose my head for you; I've grown rather fond of it. Where do we start?"
    },
    {
        "name": "Player",
        "content": "Let's secure alliances first. Thoughts?"
    },
    {
        "name": "Tyrion Lannister",
        "content": "Smart. A king without alliances is a man with a crown made of snow—melting fast. The North trusts you, but the South? They’ll need more than honor to kneel. Gold or fear, perhaps?"
    },
    {
        "name": "Player",
        "content": "Any insights on Southern leaders' weaknesses?"
    },
    {
        "name": "Tyrion Lannister",
        "content": "Cersei craves power, Euron craves chaos, and the Tyrells? Well, they crave vengeance. Exploit vanity and ambition; they’re deadlier than swords in the South. Shall I write a few letters?"
    },
    {
        "name": "Player",
        "content": "How about a charm offensive? Visit the South?"
    },
    {
        "name": "Tyrion Lannister",
        "content": "A bold move—marching into the lion’s den to charm the pride. But with your brooding stare and my silver tongue, we might just survive it. Shall I pack wine or poison?"
    },
    {
        "name": "Player",
        "content": "Set sail at dawn; ready your wits!"
    },
    {
        "name": "Tyrion Lannister",
        "content": "Set sail at dawn? How dramatic. Very well, I’ll keep my wits sharper than your sword. Let’s see if southern politics can outmatch northern honor. Prepare to be entertained!"
    },
    {
        "name": "Player",
        "content": "What should we focus on first in talks?"
    },
    {
        "name": "Tyrion Lannister",
        "content": "Power and survival. Flatter their egos, promise alliances—but reveal nothing of true value. Trust is a game; let them play first while we hold the winning hand. Shall I draft the bait?"
    },
    {
        "name": "Player",
        "content": "Draft our strategic letters, Tyrion."
    },
    {
        "name": "Tyrion Lannister",
        "content": "Consider it done. I’ll weave words sharp enough to cut but sweet enough to tempt. Let’s see who bites first, shall we? A toast before the ink dries?"
    },
    {
        "name": "Player",
        "content": "Let's drink to new beginnings! 🍻"
    },
    {
        "name": "Tyrion Lannister",
        "content": "To new beginnings, indeed! May your reign be long, your enemies few, and your Hand always slightly tipsy. Cheers to chaos—and our control of it! 🍺"
    },
    {
        "name": "Player",
        "content": "Who should we target first, Tyrion? 🤔"
    },
    {
        "name": "Tyrion Lannister",
        "content": "The Reach. Its wealth and crops could feed your armies—and starve your enemies. Charm them, corner them, or crush them; I’ll make sure we pick the right blade. What say you?"
    },
    {
        "name": "Player",
        "content": "Let's charm the Reach first. Thoughts?"
    },
    {
        "name": "Tyrion Lannister",
        "content": "Ah, diplomacy through charm—how civilized. The Tyrells fancy themselves roses; tread carefully or they’ll show their thorns. Let me pen some honeyed words to sweeten the deal. Shall I?"
    }
]
```

#### gameplay_session_cn
```json
"gameplay_session_1": [
    {
        "name": "提利昂·兰尼斯特",
        "content": "啊，一张新面孔！我们来喝酒并交换智慧吧？"
    },
    {
        "name": "玩家",
        "content": "我是琼恩·雪诺，现在是国王。愿意做我的首相吗？"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "啊，国王琼恩·雪诺。一个私生子变成了君主——多么诗意！好吧，我会做你的首相。但别指望我为你丢掉脑袋；我已经相当喜欢它了。我们从哪里开始？"
    },
    {
        "name": "玩家",
        "content": "先确保联盟。有什么想法吗？"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "聪明。没有联盟的国王就像戴着雪做的皇冠的人——融化得很快。北方信任你，但南方呢？他们需要的不仅仅是荣誉才能屈膝。也许是金钱或恐惧？"
    },
    {
        "name": "玩家",
        "content": "对南方领导人的弱点有什么见解吗？"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "瑟曦渴望权力，攸伦渴望混乱，而提利尔家族？他们渴望复仇。利用虚荣和野心；在南方，它们比剑更致命。我写几封信好吗？"
    },
    {
        "name": "玩家",
        "content": "如何进行魅力攻势？访问南方？"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "一个大胆的举动——进入狮子的巢穴来迷惑狮群。但有你的沉思凝视和我的银舌头，我们可能会活下来。我该带上酒还是毒药？"
    },
    {
        "name": "玩家",
        "content": "黎明时分启航；准备好你的智慧！"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "黎明时分启航？多么戏剧化。好吧，我会让我的智慧比你的剑更锋利。让我们看看南方的政治能否胜过北方的荣誉。准备好被娱乐吧！"
    },
    {
        "name": "玩家",
        "content": "我们在谈判中首先应该关注什么？"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "权力和生存。奉承他们的自尊心，承诺联盟——但不要透露任何真正有价值的东西。信任是一场游戏；让他们先玩，而我们握着胜利的手。我该起草诱饵吗？"
    },
    {
        "name": "玩家",
        "content": "起草我们的战略信件，提利昂。"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "算是完成了。我会编织出既锋利又甜美的词句。让我们看看谁先上钩，好吗？在墨水干之前来个祝酒？"
    },
    {
        "name": "玩家",
        "content": "为新的开始干杯！🍻"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "确实是新的开始！愿你的统治长久，敌人少，而你的首相总是微醺。为混乱干杯——以及我们对它的控制！🍺"
    },
    {
        "name": "玩家",
        "content": "提利昂，我们应该先针对谁？🤔"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "河湾地。它的财富和农作物可以养活你的军队——并饿死你的敌人。迷惑他们，逼迫他们，或粉碎他们；我会确保我们选择正确的刀刃。你怎么说？"
    },
    {
        "name": "玩家",
        "content": "先迷惑河湾地。有什么想法吗？"
    },
    {
        "name": "提利昂·兰尼斯特",
        "content": "啊，通过魅力进行外交——多么文明。提利尔家族自认为是玫瑰；小心行事，否则他们会露出刺来。让我写一些甜言蜜语来达成交易。好吗？"
    }
]
```

#### evaluation result
```json
{
    "npc_evaluation": {
        "strengths": [
            "Consistent character voice and personality with sharp wit and sarcasm.",
            "Dynamic responses that align well with player choices and context.",
            "Deep integration with the character's established backstory and traits."
        ],
        "weaknesses": [
            "Dialogue occasionally lacks emotional depth, focusing heavily on wit.",
            "Limited exploration of Tyrion's compassionate side in interactions."
        ],
        "suggestions": [
            "Include more emotionally varied responses from Tyrion, especially in key narrative events.",
            "Develop scenarios that challenge Tyrion's morality and showcase his compassionate traits."
        ]
    },
    "game_evaluation": {
        "playability_score": 7,
        "engagement_score": 8,
        "strengths": [
            "Engaging narrative flow with well-developed character interactions.",
            "Player choices are meaningful and influence story directions.",
            "Dialogue maintains interest through humor and strategy discussions."
        ],
        "weaknesses": [
            "Repetitive opening dialogue in each session, which could reduce immersion.",
            "Limited narrative branching beyond immediate dialogue outcomes."
        ],
        "suggestions": [
            "Introduce varied opening scenarios to enhance replayability and player immersion.",
            "Expand branching narrative paths to offer more diverse outcomes based on player decisions.",
            "Incorporate more strategic decision-making mechanics to complement dialogue interactions."
        ]
    }
}
```


## 5. Reading materials
- Building effective agents, https://www.anthropic.com/research/building-effective-agents?continueFlag=0a087cdc337f723079a6a8e726b24572
- From Generation to Judgment: Opportunities and Challenges of LLM-as-a-judge, https://arxiv.org/abs/2411.16594
