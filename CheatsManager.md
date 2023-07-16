# 作弊码功能

基本思路：利用UI中的输入字段来制作输入框，通过列表存储作弊码，在输入结束后根据是否符合来决定是否调用相应函数，此处选择继承范式单例制作CheatsManager脚本，然后Canvas挂载UI脚本，来调用对应函数，其中部分作弊方法实现后文叙述。



1. 创建Cheat Canvas，其中继续创建Panel，然后创建输入字段（InputField）

2. 挂载Cheats UI Manager脚本

脚本内容如下

```c#
public GameObject cheatPanel;
public TMP_InputField cheatInput;   //使用TMP，需要using TMPro;
private bool isCheatPanelActive = false;

    void Update()
    {
        if (Input.GetKeyUp(KeyCode.Return))
        {
            ToggleCheatPanel();
        }
    }

public void CheckCheatCode()
{
    string inputCode = cheatInput.text.ToLower();
    
    if (inputCode == "")
    {
        ...
    }
    else if (inputCode = "")
    {
        ...
    }
    
    ClearInputField();//清空
    
    void ToggleCheatPanel()
    {
        isCheatPanelActive = !isCheatPanelActive;
        cheatPanel.SetActive(isCheatPanelActive);
        if (isCheatPanelActive)
        {
            cheatInput.text = ""; // 清空输入框内容
            cheatInput.Select();  // 设置输入框为活动状态
        }
    }

    void ClearInputField()
    {
        cheatInput.text = "";  // 清空输入框内容
        cheatInput.Select();   // 设置输入框为活动状态
    }
}
```

3. 在CheatsManager中实现对应作弊码以及函数

脚本部分内容如下

```c#
public List<string> cheatCodes;//作弊码列表

//还需要引用对应需要的内容，例如人物，例如背包，来更改相应内容，具体根据代码而定
void Start()
    {
        cheatCodes = new List<string>()
        {
            "mhealth",   //回复至血量上限
            "inshealth", //无敌模式
            "jumpt",     //"多"次跳跃
            "hjump"      //跳跃力度提升 
            // 其他作弊码，等完成武器系统后继续，飞天，无技能CD有时间再加

            //获得武器
            //获得药水
            //伤害提升
    };
    
```

实现思路如下



+ 如果需要回复血量，那么获取玩家实例，然后回复血量
+ 如果需要修改跳跃，同样获取玩家实例，然后回复血量
+ 如果需要更改道具，为背包添加数据即可
+ 如果需要修改伤害，那么修改武器数据，或者修改玩家基础伤害
+ CD同理