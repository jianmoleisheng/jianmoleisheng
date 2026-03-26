# 缄默的个人作品集 (Jianmo's Portfolio) 🚀

欢迎来到我的个人主页源码仓库！这是一个基于 HTML/CSS/JS 原生开发的响应式单页应用（SPA），用于展示我的全栈开发技能、核心项目以及跨学科的实践经历。

🌍 **在线预览我的个人网站：** [点击这里访问我的 GitHub Pages]([https://jianmoleisheng.github.io/jianmoleisheng](https://github.com/jianmoleisheng/jianmoleisheng/edit/main/README.md#L5C91))

---

## 🛠️ 技术栈与核心能力

* **后端与架构**：Java Core, 面向对象编程 (OOP), MySQL 数据库设计
* **前端交互**：HTML5, CSS3, JavaScript (ES6+), 响应式布局, 原生 DOM 操作
* **综合与前沿**：Python 数据处理, OpenClaw AI 代理配置, Blender 3D 建模, 概率统计与业务逻辑建模

---

## 💻 核心项目亮点展示

### 1. 个人财务健康诊断与可视化分析系统 (Java + 宏观经济模型)
这是我目前正在主力开发的系统。不仅包含常规的增删改查，更核心的是将经济学模型转化为实际的代码逻辑。

**核心诊断算法示例（Java）：**
```java
// 结合宏观经济与个人理财模型的财务健康度评估
public class FinancialAnalyzer {
    
    public String evaluateHealth(double income, double expense, double debt) {
        double savingsRate = (income - expense) / income;
        double debtRatio = debt / income;
        int healthScore = 100;

        // 核心风控扣分逻辑
        if (savingsRate < 0.2) healthScore -= 20;
        if (debtRatio > 0.5) healthScore -= 30;
        
        if (healthScore >= 80) return "良好: 现金流健康，抗风险能力强";
        else if (healthScore >= 60) return "预警: 建议优化收支结构，降低负债";
        else return "危险: 存在高杠杆风险，需重组债务";
    }
}
