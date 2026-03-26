# Engineering Portfolio & Knowledge Base

> **项目状态**: 持续迭代中 (Active Development) <br>
> **访问节点**: [GitHub Pages 生产环境直达]([jianmoleisheng.github.io])

## 1. 工程概述 (Engineering Overview)

本项目为个人工程实践与技术架构展示的综合代码库。整体采用模块化设计理念，涵盖从底层业务逻辑建模、数据持久层交互、到前端视图层渲染的全链路开发闭环。旨在展示面对复杂业务场景时的系统性拆解能力、代码规范性以及对跨学科领域（如宏观经济模型、概率统计与 AI Agent）的工程化落地能力。

---

## 2. 技术栈架构矩阵 (Architecture & Tech Stack Matrix)

| 领域 (Domain) | 核心技术与组件 (Core Technologies) | 工程实践重点 (Engineering Focus) |
| :--- | :--- | :--- |
| **Backend & Data** | Java Core, 面向对象设计, MySQL | 业务模型抽象, 复杂风控逻辑处理, 关系型数据库设计 |
| **Frontend & UI** | HTML5, CSS3, JavaScript (ES6+) | 响应式布局, 原生 DOM 渲染性能, 无第三方依赖组件开发 |
| **AI & Automation** | Python, OpenClaw AI Agent, LLM API | Prompt 调优, 自动化工作流编排, API 接口联调 |
| **3D & Math Models** | Blender, 概率统计, 线性代数 | 3D 资产管线构建, 游戏数值模型分析, 跨学科逻辑推演 |

---

## 3. 核心业务模块与系统实现 (Core System Implementations)

### 3.1 个人财务健康度诊断与可视化风控系统
本项目为底层逻辑重后端的分析系统，旨在通过量化模型评估个体财务抗风险能力。

* **架构分层**: 采用标准的 MVC 分层思想，剥离数据访问与业务计算。
* **业务实现**: 将宏观经济学原理（如 IS-LM 模型中的流动性偏好）与个人理财体系结合，构建动态评分指标。
* **核心代码示例 (评估引擎模块)**:

```java
/**
 * 财务风控评估引擎 (Financial Risk Assessment Engine)
 * 职责：接收结构化财务数据，执行风控规则拦截并输出定级报告。
 */
public class FinancialAnalyzer {
    
    // 阈值常量定义，便于后期接入配置中心动态调整
    private static final double MIN_SAVINGS_RATE_THRESHOLD = 0.20;
    private static final double MAX_DEBT_RATIO_THRESHOLD = 0.50;
    
    public String evaluateHealth(double income, double expense, double debt) {
        // 核心指标计算
        double savingsRate = calculateRatio(income - expense, income);
        double debtRatio = calculateRatio(debt, income);
        int healthScore = 100;

        // 执行风控扣分策略
        if (savingsRate < MIN_SAVINGS_RATE_THRESHOLD) healthScore -= 20;
        if (debtRatio > MAX_DEBT_RATIO_THRESHOLD) healthScore -= 30;
        
        // 输出诊断评级
        return generateReport(healthScore);
    }

    private double calculateRatio(double numerator, double denominator) {
        return denominator == 0 ? 0 : numerator / denominator;
    }
    
    private String generateReport(int score) {
        if (score >= 80) return "状态：良好 (A级) - 现金流健康，抗风险能力充足";
        if (score >= 60) return "状态：预警 (B级) - 触发负债率阈值，需优化资产结构";
        return "状态：危险 (C级) - 高杠杆风险暴露，建议立即重组债务";
    }
}
