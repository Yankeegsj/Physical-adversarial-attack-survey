# 面向光电智能感知安全的物理对抗样本研究进展与趋势

<p align="center">
  <img alt="Paper Type" src="https://img.shields.io/badge/Paper-Survey-blue">
  <img alt="Focus" src="https://img.shields.io/badge/Focus-Physical%20Adversarial%20Examples-red">
  <img alt="Modalities" src="https://img.shields.io/badge/Modalities-RGB%20%7C%20IR%20%7C%20LiDAR%20%7C%20Multimodal-green">
  <img alt="Status" src="https://img.shields.io/badge/Status-Continuously%20Updated-orange">
</p>

> 这是一个面向 **光电智能感知安全** 的物理对抗样本文献索引主页。  
> 以综述论文 **《面向光电智能感知安全的物理对抗样本研究进展与趋势》** 为主线，持续整理和追踪 **可见光、红外、激光雷达、多模态、以及防御策略** 方向的论文。

---

## 论文信息

- **论文题目**：面向光电智能感知安全的物理对抗样本研究进展与趋势
- **作者**：杨星，龚申健，梁振宇，林志，胡至洋
- **单位**：国防科技大学电子对抗学院
- **论文类型**：综述论文
- **用途定位**：GitHub 仓库首页 / 文献导航页 / 方向入门索引

## 简介

本文系统综述了光电智能感知系统中的物理对抗样本研究进展，围绕 **物理对抗样本的定义、实现流程、介质形式、鲁棒性约束与效能评估** 展开，并进一步从 **单模态到多模态融合** 的演进脉络梳理现有工作。

按照论文主体结构，本文重点覆盖以下五条主线：

- **可见光物理对抗样本**：表面附着式、非接触光场调控式、目标本体改造式。  
  这一方向主要依托相机成像链路，通过贴纸、伪装纹理、服饰载体、投影、激光、阴影等方式改变目标在图像空间中的外观表达。其核心目标是在真实拍摄条件下维持跨视角、跨距离、跨光照的攻击鲁棒性，同时兼顾物理可部署性与隐蔽性。

- **红外物理对抗样本**：基于隔热材料的无源攻击、基于主动热源的有源攻击。  
  这类方法面向热成像机理，不再单纯操控颜色纹理，而是直接操控目标表面的热辐射分布。无源方法通常利用材料热属性改变表观温度分布，有源方法则通过灯泡、冷热模块、加热单元等主动塑造热模式，从而实现对红外检测器的误导。

- **激光雷达单模态物理对抗样本**：激光脉冲欺骗、三维网格优化、多物理场耦合。  
  这一方向围绕 LiDAR 点云感知链路展开，攻击既可以直接作用于传感器接收过程，伪造或抑制回波点，也可以通过设计三维物体形状、表面和场景布局来改变点云几何结构。相比视觉模态，LiDAR 攻击更强调距离采样机理、空间几何一致性与传感器物理工作机制。

- **多模态物理对抗样本**：围绕融合架构脆弱性、输入层 / 特征层 / 决策层攻击展开。  
  随着可见光、红外、LiDAR 等传感器联合感知成为主流，攻击者需要同时考虑不同模态的表征差异与融合策略缺陷。该方向既研究统一物理载体如何同时干扰多个模态，也分析早期融合、中期融合、后期融合在跨模态对齐、注意力分配与决策整合方面的脆弱性。

- **防御策略**：输入层预处理、模型训练与结构增强、对抗检测与后处理校正。  
  防御研究不再局限于单一滤波或单一训练技巧，而是形成了多层次体系。输入层方法尝试在进入模型前净化或破坏扰动，训练与结构增强方法直接提升模型鲁棒性，对抗检测与后处理方法则侧重识别异常样本、定位局部补丁并进行抑制或校正。

## 引用方式

```bibtex
@article{yang2025physicaladversarialsurvey,
  title   = {面向光电智能感知安全的物理对抗样本研究进展与趋势},
  author  = {杨星 and 龚申健 and 梁振宇 and 林志 and 胡至洋},
  journal = {待补充正式刊物信息},
  year    = {2025}
}
```

## 仓库更新日志

- **2026-03-15**：完成仓库首页精修与结构统一，保留综述主线下的 **可见光、红外、激光雷达、多模态与防御策略** 五大方向；补充分类解释表、统一表格字段与跳转目录，并按发表时间整理相关论文。

---

## 分类目录

- [可见光物理对抗样本](#可见光物理对抗样本)
- [红外物理对抗样本](#红外物理对抗样本)
- [激光雷达物理对抗样本](#激光雷达物理对抗样本)
- [多模态物理对抗样本](#多模态物理对抗样本)
- [防御策略](#防御策略)

---

## 可见光物理对抗样本

| 分类 | 含义说明 |
|---|---|
| 表面附着式 | 指将贴纸、补丁、标识、荧光介质等直接附着在目标表面或其邻近区域，通过改变局部可见外观来诱导识别或检测错误。该类方法实现简单、部署直接，是最常见的物理攻击形式之一。 |
| 非接触光场调控式 | 指不直接改造目标表面，而是借助投影、激光、阴影、半透明介质等方式调控进入相机的光场分布。其优势在于可重复操作、隐蔽性较强，但往往更依赖环境条件与设备控制精度。 |
| 目标本体改造式 | 指把对抗设计融入目标整体外观或载体本体，例如整车伪装、服饰纹理、帽子、妆容等。该类方法更强调跨视角、跨距离和跨场景的持续攻击能力，也更接近真实部署场景。 |

| 论文题目 | 发表时间 | 出版社 | 所属分类 | 所提的方法名称 | 该方法的核心思想描述 |
|---|---:|---|---|---|---|
| [Accessorize to a Crime: Real and Stealthy Attacks on State-of-the-art Face Recognition](https://dl.acm.org/doi/10.1145/2976749.2978392) | 2016年 | ACM CCS | 表面附着式 / 可穿戴伪装 | Accessorize to a Crime | 利用眼镜框等可穿戴载体实施真实人脸识别攻击，强调物理可部署性与隐蔽性。 |
| [Adversarial Patch](https://arxiv.org/abs/1712.09665) | 2017年 | NeurIPS Workshop | 表面附着式 | Adversarial Patch | 提出通用、可打印、场景无关的局部补丁攻击范式。 |
| [Robust Physical-World Attacks on Deep Learning Visual Classification](https://openaccess.thecvf.com/content_cvpr_2018/html/Eykholt_Robust_Physical-World_Attacks_CVPR_2018_paper.html) | 2018年 | CVPR | 表面附着式 | RP2 | 通过贴纸扰动真实交通标志，使分类模型在不同距离与视角下稳定误判，是物理对抗攻击的早期里程碑。 |
| [Projecting Trouble: Light Based Adversarial Attacks on Deep Learning Classifiers](https://arxiv.org/abs/1810.10337) | 2018年 | arXiv | 非接触光场调控式 | Light Projection Attack | 通过投影光场而非粘贴介质注入扰动，属于非接触式可见光攻击。 |
| [CAMOU: Learning Physical Vehicle Camouflages to Adversarially Attack Detectors in the Wild](https://scholar.google.com/scholar?q=CAMOU%3A%20Learning%20Physical%20Vehicle%20Camouflages%20to%20Adversarially%20Attack%20Detectors%20in%20the%20Wild) | 2019年 | ICLR | 目标本体改造式 | CAMOU | 在整车表面学习连续伪装纹理，使目标检测器在多视角场景下持续漏检或误检。 |
| [Fooling Automated Surveillance Cameras: Adversarial Patches to Attack Person Detection](https://scholar.google.com/scholar?q=Fooling%20Automated%20Surveillance%20Cameras%3A%20Adversarial%20Patches%20to%20Attack%20Person%20Detection) | 2019年 | CVPR Workshops | 表面附着式 / 可穿戴伪装 | advYOLO Patch | 将对抗补丁扩展到行人检测任务，降低监控场景下人体被检出概率。 |
| [Perceptual-Sensitive GAN for Generating Adversarial Patches](https://scholar.google.com/scholar?q=Perceptual-Sensitive%20GAN%20for%20Generating%20Adversarial%20Patches) | 2019年 | AAAI | 表面附着式 | PS-GAN | 引入感知约束与GAN生成机制，使补丁兼顾攻击性与视觉自然性。 |
| [Adversarial T-shirt! Evading Person Detectors in a Physical World](https://scholar.google.com/scholar?q=Adversarial%20T-shirt%21%20Evading%20Person%20Detectors%20in%20a%20Physical%20World) | 2019年 | arXiv | 目标本体改造式 / 可穿戴伪装 | Adversarial T-shirt | 把对抗纹理部署在T恤等服饰上，实现可穿戴行人检测逃逸。 |
| [Universal Physical Camouflage Attacks on Object Detectors](https://scholar.google.com/scholar?q=Universal%20Physical%20Camouflage%20Attacks%20on%20Object%20Detectors) | 2020年 | CVPR | 目标本体改造式 | Universal Camouflage | 将扰动从局部补丁扩展为更大范围伪装图案，提升跨视角鲁棒性。 |
| [Making an Invisibility Cloak: Real World Adversarial Attacks on Object Detectors](https://www.ecva.net/papers/eccv_2020/papers_ECCV/html/4389_ECCV_2020_paper.php) | 2020年 | ECCV | 目标本体改造式 / 可穿戴伪装 | Invisibility Cloak | 基于服饰/织物载体设计可穿戴对抗图案，削弱人体目标检测性能。 |
| [Adversarial Light Projection Attacks on Face Recognition Systems: A Feasibility Study](https://scholar.google.com/scholar?q=Adversarial%20Light%20Projection%20Attacks%20on%20Face%20Recognition%20Systems%3A%20A%20Feasibility%20Study) | 2020年 | CVPR Workshops | 非接触光场调控式 | ALPA | 研究投影式光照扰动对人脸识别系统的可行性攻击。 |
| [Adversarial Camouflage: Hiding Physical-World Attacks with Natural Styles](https://scholar.google.com/scholar?q=Adversarial%20Camouflage%3A%20Hiding%20Physical-World%20Attacks%20with%20Natural%20Styles) | 2020年 | CVPR | 目标本体改造式 | Adversarial Camouflage | 使用自然风格伪装降低对抗图案被人察觉的概率。 |
| [Towards a Physical-World Adversarial Patch for Blinding Object Detection Models](https://scholar.google.com/scholar?q=Towards%20a%20Physical-World%20Adversarial%20Patch%20for%20Blinding%20Object%20Detection%20Models) | 2021年 | Information Sciences | 表面附着式 | Blinding Patch | 面向目标检测器优化可物理打印补丁，在真实拍摄条件下实现致盲攻击。 |
| [Dual Attention Suppression Attack: Generate Adversarial Camouflage in Physical World](https://scholar.google.com/scholar?q=Dual%20Attention%20Suppression%20Attack%3A%20Generate%20Adversarial%20Camouflage%20in%20Physical%20World) | 2021年 | CVPR | 目标本体改造式 | DAS | 压制检测器的空间与通道注意力响应，生成更具物理鲁棒性的伪装扰动。 |
| [Adversarial Laser Beam: An Effective Physical-World Attack to DNNs](https://scholar.google.com/scholar?q=Adversarial%20Laser%20Beam%3A%20An%20Effective%20Physical-World%20Attack%20to%20DNNs) | 2021年 | arXiv | 非接触光场调控式 | Laser Beam Attack | 利用激光束在成像面上制造高亮扰动，干扰视觉分类/检测模型。 |
| [The Translucent Patch: A Physical and Universal Attack on Object Detectors](https://openaccess.thecvf.com/content/CVPR2021/html/Liu_The_Translucent_Patch_A_Physical_and_Universal_Attack_on_Object_Detectors_CVPR_2021_paper.html) | 2021年 | CVPR | 非接触光场调控式 | Translucent Patch / SLAP | 将半透明补丁置于镜头附近，以非接触方式同时干扰整幅图像的检测结果。 |
| [AdvHat: Real-world Adversarial Attack on ArcFace Face ID System](https://scholar.google.com/scholar?q=AdvHat%3A%20Real-world%20Adversarial%20Attack%20on%20ArcFace%20Face%20ID%20System) | 2021年 | ICPR | 目标本体改造式 / 可穿戴伪装 | AdvHat | 将扰动部署在帽子等头部饰品上，攻击现实人脸识别系统。 |
| [AdvMakeup: A New Imperceptible and Transferable Attack on Face Recognition](https://www.ijcai.org/proceedings/2021/175) | 2021年 | IJCAI | 目标本体改造式 / 可穿戴伪装 | AdvMakeup | 利用化妆式隐蔽扰动攻击人脸识别，强调迁移性与自然外观。 |
| [FCA: Learning a 3D Full-Coverage Vehicle Camouflage for Multi-view Physical Adversarial Attack](https://ojs.aaai.org/index.php/AAAI/article/view/20117) | 2022年 | AAAI | 目标本体改造式 | FCA | 学习覆盖整车三维曲面的连续伪装，实现多视角稳定攻击。 |
| [DTA: Physical Camouflage Attacks Using Differentiable Transformation Network](https://openaccess.thecvf.com/content/CVPR2022/html/Wang_DTA_Physical_Camouflage_Attacks_Using_Differentiable_Transformation_Network_CVPR_2022_paper.html) | 2022年 | CVPR | 目标本体改造式 | DTA | 用可微变换网络显式建模物理拍摄过程，提高数字到物理迁移效果。 |
| [Adversarial Texture for Fooling Person Detectors in the Physical World](https://openaccess.thecvf.com/content/CVPR2022/html/Xu_Adversarial_Texture_for_Fooling_Person_Detectors_in_the_Physical_World_CVPR_2022_paper.html) | 2022年 | CVPR | 目标本体改造式 / 可穿戴伪装 | AdvTexture | 针对人体形变与布料褶皱设计周期可扩展纹理，提升服饰攻击鲁棒性。 |
| [Shadows Can Be Dangerous: Stealthy and Effective Physical-World Adversarial Attack by Natural Phenomenon](https://openaccess.thecvf.com/content/CVPR2022/html/Xiao_Shadows_Can_Be_Dangerous_Stealthy_and_Effective_Physical-World_Adversarial_Attack_CVPR_2022_paper.html) | 2022年 | CVPR | 非接触光场调控式 | Shadow Attack | 借助自然阴影这一低显著性现象构造高隐蔽性的物理攻击。 |
| [Adversarial Sticker: A Stealthy Attack Method in the Physical World](https://scholar.google.com/scholar?q=Adversarial%20Sticker%3A%20A%20Stealthy%20Attack%20Method%20in%20the%20Physical%20World) | 2022年 | IEEE TPAMI | 表面附着式 | Adversarial Sticker | 通过隐蔽贴纸攻击视觉模型，兼顾物理可实现性与不显眼外观。 |
| [DiffPatch: Generating Customizable Adversarial Patches Using Diffusion Model](https://arxiv.org/abs/2412.01440) | 2024年 | arXiv | 表面附着式 | DiffPatch | 用扩散模型生成更灵活、可定制的对抗补丁。 |
| [The Fluorescent Veil: A Stealthy and Effective Physical Adversarial Patch Against Traffic Sign Recognition](https://arxiv.org/abs/2409.12394) | 2024年 | arXiv | 表面附着式 | Fluorescent Veil | 利用荧光介质提升贴片隐蔽性，同时保持对交通标志识别的攻击效果。 |
| [Invisible Triggers, Visible Threats! Road-Style Adversarial Creation Attack for Visual 3D Detection in Autonomous Driving](https://arxiv.org/abs/2511.08015) | 2025年 | arXiv | 目标本体改造式 / 场景级伪装 | Road-Style Attack | 通过道路风格触发器攻击自动驾驶视觉3D检测模型，属于可见光场景伪装思路延伸。 |

---

## 红外物理对抗样本

| 分类 | 含义说明 |
|---|---|
| 基于隔热材料的无源攻击 | 指通过隔热、反射、低发射率等材料改变目标的热辐射分布，而不额外提供主动能量输入。这类方法更强调材料热学属性设计，通常隐蔽性较好、持续性较强。 |
| 基于主动热源的有源攻击 | 指利用灯泡、加热片、冷热模块等主动热源塑造特定温度模式，从而欺骗红外传感器。该类方法调控能力更强，但通常需要供能，并会带来部署复杂度与可见性问题。 |

| 论文题目 | 发表时间 | 出版社 | 所属分类 | 所提的方法名称 | 该方法的核心思想描述 |
|---|---:|---|---|---|---|
| [Fooling Thermal Infrared Pedestrian Detectors in Real World Using Small Bulbs](https://ojs.aaai.org/index.php/AAAI/article/view/16477) | 2021年 | AAAI | 基于主动热源的有源攻击 | advBulbs | 用小灯泡阵列主动调控热分布，在热红外成像中形成误导性热点/冷点。 |
| [Infrared Invisible Clothing: Hiding from Infrared Detectors at Multiple Angles in Real World](https://openaccess.thecvf.com/content/CVPR2022/html/Zhu_Infrared_Invisible_Clothing_Hiding_From_Infrared_Detectors_at_Multiple_Angles_CVPR_2022_paper.html) | 2022年 | CVPR | 基于隔热材料的无源攻击 | Infrared Invisible Clothing | 将热对抗图案与服装结合，并显式考虑多角度观察约束。 |
| [HOTCOLD Block: Fooling Thermal Infrared Detectors with a Novel Wearable Design](https://ojs.aaai.org/index.php/AAAI/article/view/26777) | 2023年 | AAAI | 基于主动热源的有源攻击 | HotCold Block | 通过冷热模块组合塑造热轮廓，实现更易部署的可穿戴红外攻击。 |
| [Physically Adversarial Infrared Patches with Learnable Shapes and Locations](https://openaccess.thecvf.com/content/CVPR2023/html/Wei_Physically_Adversarial_Infrared_Patches_With_Learnable_Shapes_and_Locations_CVPR_2023_paper.html) | 2023年 | CVPR | 基于主动热源的有源攻击 | LSLP | 联合优化红外补丁的形状、位置与热分布，兼顾尺寸效率与物理可实现性。 |
| [Adversarial Infrared Curves: An Attack on Infrared Pedestrian Detectors in the Physical World](https://scholar.google.com/scholar?q=Adversarial%20Infrared%20Curves%3A%20An%20Attack%20on%20Infrared%20Pedestrian%20Detectors%20in%20the%20Physical%20World) | 2024年 | Neural Networks | 基于主动热源的有源攻击 | Infrared Curves | 使用曲线式热扰动增强贴合人体形状的攻击表现。 |
| [Adversarial Infrared Blocks: A Multi-view Black-box Attack to Thermal Infrared Detectors in Physical World](https://scholar.google.com/scholar?q=Adversarial%20Infrared%20Blocks%3A%20A%20Multi-view%20Black-box%20Attack%20to%20Thermal%20Infrared%20Detectors%20in%20Physical%20World) | 2024年 | Neural Networks | 基于主动热源的有源攻击 | Infrared Blocks | 在黑盒条件下通过块状热扰动实现多视角红外攻击。 |
| [Adversarial Infrared Geometry: Using Geometry to Perform Adversarial Attack against Infrared Pedestrian Detectors](https://scholar.google.com/scholar?q=Adversarial%20Infrared%20Geometry%3A%20Using%20Geometry%20to%20Perform%20Adversarial%20Attack%20against%20Infrared%20Pedestrian%20Detectors) | 2024年 | arXiv | 基于主动热源的有源攻击 | Infrared Geometry | 从几何布局而非单纯纹理出发设计热红外扰动。 |
| [Physical Adversarial Examples for Person Detectors in Thermal Images Based on 3D Modeling](https://scholar.google.com/scholar?q=Physical%20Adversarial%20Examples%20for%20Person%20Detectors%20in%20Thermal%20Images%20Based%20on%203D%20Modeling) | 2025年 | IEEE TPAMI | 基于隔热材料的无源攻击 / 三维建模 | Adv3DM | 利用人体三维建模提升热红外对抗样本在多视角曲面条件下的鲁棒性。 |
| [AdvGrid: A Multi-view Black-box Attack on Infrared Pedestrian Detectors in the Physical World](https://scholar.google.com/scholar?q=AdvGrid%3A%20A%20Multi-view%20Black-box%20Attack%20on%20Infrared%20Pedestrian%20Detectors%20in%20the%20Physical%20World) | 2025年 | Applied Soft Computing | 基于主动热源的有源攻击 | AdvGrid | 采用网格化结构与多视角黑盒优化，提高红外攻击迁移性与稳定性。 |

---

## 激光雷达物理对抗样本

| 分类 | 含义说明 |
|---|---|
| 激光脉冲欺骗 | 指直接干扰 LiDAR 发射—接收链路，通过伪造、注入或覆盖回波信号来制造虚假点、虚假目标或距离偏差。这类方法更贴近传感器底层工作机制。 |
| 三维网格优化 | 指通过优化三维物体的几何形状、网格结构或表面布局，改变传感器采样到的点云分布，使下游感知模型产生误判。其核心在于几何可实现性与物理可制造性。 |
| 多物理场耦合 | 指综合考虑反射特性、空间几何、传感器扫描方式以及环境交互等因素，对 LiDAR 感知过程进行更复杂的联合操控。该类方法通常更接近真实场景中的系统级攻击。 |

| 论文题目 | 发表时间 | 出版社 | 所属分类 | 所提的方法名称 | 该方法的核心思想描述 |
|---|---:|---|---|---|---|
| [Adversarial Sensor Attack on LiDAR-based Perception in Autonomous Driving](https://dl.acm.org/doi/10.1145/3319535.3363210) | 2019年 | ACM CCS | 激光脉冲欺骗 | Adversarial Sensor Attack | 通过向LiDAR注入伪造回波点，干扰三维感知与目标检测，是单模态LiDAR物理攻击的代表性起点。 |
| [Towards Robust LiDAR-based Perception in Autonomous Driving: General Black-box Adversarial Sensor Attack and Countermeasures](https://www.usenix.org/conference/usenixsecurity20/presentation/sun) | 2020年 | USENIX Security | 激光脉冲欺骗 / 黑盒攻击 | Black-box Sensor Attack | 研究一般黑盒条件下的LiDAR传感器欺骗与对应缓解策略。 |
| [Physically Realizable Adversarial Examples for LiDAR Object Detection](https://openaccess.thecvf.com/content_CVPR_2020/html/Tu_Physically_Realizable_Adversarial_Examples_for_LiDAR_Object_Detection_CVPR_2020_paper.html) | 2020年 | CVPR | 三维网格优化 | Physically Realizable Adv Example | 在三维空间中优化目标物体形状/表面，使点云检测器在真实采样下持续失效。 |
| [Robust Roadside Physical Adversarial Attack against Deep Learning in LiDAR Perception Modules](https://dl.acm.org/doi/10.1145/3464374.3481013) | 2021年 | ACM AsiaCCS | 三维网格优化 / 路侧攻击 | Roadside Physical Attack | 将攻击部署到道路侧基础设施或场景物体上，提升物理世界中的可实施性。 |
| [You Can't See Me: Physical Removal Attacks on LiDAR-based Autonomous Vehicles Driving Frameworks](https://www.usenix.org/conference/usenixsecurity23/presentation/cao-yulong) | 2023年 | USENIX Security | 激光脉冲欺骗 / 目标移除 | Physical Removal Attack | 利用物理干预制造“目标消失”现象，破坏自动驾驶系统对障碍物的检测。 |
| [PLA-LiDAR: Physical Laser Attacks against LiDAR-based 3D Object Detection in Autonomous Vehicle](https://ieeexplore.ieee.org/document/10179379) | 2023年 | IEEE S&P | 激光脉冲欺骗 | PLA-LiDAR | 直接针对LiDAR发射/接收过程实施物理激光攻击，实现3D目标检测误导。 |
| [EMI-LiDA: Electromagnetic Interference-based LiDAR Denial Attack on Autonomous Vehicles](https://ieeexplore.ieee.org/document/10517563) | 2024年 | IEEE TIFS | 多物理场耦合 | EMI-LiDA | 借助电磁干扰破坏LiDAR工作状态，属于多物理场耦合式拒止攻击。 |
| [LiDAR Point Cloud Transmission: Adversarial Perspectives of Spoofing Attacks in Autonomous Driving](https://www.sciencedirect.com/science/article/pii/S0167404825001534) | 2025年 | Computers & Security | 激光脉冲欺骗 / 传输链路欺骗 | Point Cloud Spoofing | 从点云传输与欺骗角度系统讨论LiDAR单模态攻击面。 |
| [LiDAttack: Robust Black-box Attack on LiDAR-based Object Detection](https://ieeexplore.ieee.org/document/11006473) | 2025年 | IEEE TITS | 三维网格优化 / 黑盒攻击 | LiDAttack | 面向LiDAR检测器设计鲁棒黑盒攻击策略，减少对白盒信息的依赖。 |
| [OBJVANISH: Physically Realizable Text-to-3D Adversarial Generation of LiDAR-invisible Objects](https://scholar.google.com/scholar?q=OBJVANISH%3A%20Physically%20realizable%20text-to-3D%20adversarial%20generation%20of%20LiDAR-invisible%20objects) | 2025年 | arXiv | 三维网格优化 / 生成式设计 | OBJVANISH | 通过文本到3D生成框架构造LiDAR不可见物体，强调生成式设计能力。 |
| [Revisiting Physically Realizable Adversarial Object Attack against LiDAR-based Detection: Clarifying Problem Formulation and Experimental Protocols](https://scholar.google.com/scholar?q=Revisiting%20physically%20realizable%20adversarial%20object%20attack%20against%20LiDAR-based%20detection%3A%20Clarifying%20problem%20formulation%20and%20experimental%20protocols) | 2025年 | AAAI | 三维网格优化 / 协议重审 | Revisiting LiDAR Attack | 重新审视LiDAR物理对抗对象攻击的设定与实验协议，澄清评测标准。 |

---

## 多模态物理对抗样本

| 分类 | 含义说明 |
|---|---|
| 融合架构脆弱性 | 指研究多模态融合系统在结构设计上的天然弱点，例如模态对齐误差、特征依赖不均衡或决策耦合失衡。此类工作不一定直接提出统一攻击介质，但会揭示可被利用的关键攻击面。 |
| 输入层攻击 | 指在传感器输入侧设计统一物理载体，同时干扰两个或多个模态的原始观测结果，例如同时影响可见光与红外、或相机与 LiDAR 的输入。 |
| 特征层攻击 | 指攻击融合网络的中间特征表达，通过破坏跨模态特征对齐、注意力分配或表示一致性来削弱融合性能。 |
| 决策层攻击 | 指面向后期融合或检测决策阶段实施攻击，扰乱不同模态输出的组合方式，使系统在最终判断时出现错误。 |

| 论文题目 | 发表时间 | 出版社 | 涉及模态 | 所属分类 | 所提的方法名称 | 该方法的核心思想描述 |
|---|---:|---|---|---|---|---|
| [Adversarial Attacks on Camera-LiDAR Models for 3D Car Detection](https://ieeexplore.ieee.org/document/9636638) | 2021年 | IEEE IROS | Camera + LiDAR | 输入层攻击 | 3D Adversarial Object | 在目标车上部署具有特定几何与纹理的三维物体，同时干扰图像与点云。 |
| [Invisible for both Camera and LiDAR: Security of Multi-Sensor Fusion based Perception in Autonomous Driving under Physical-World Attacks](https://arxiv.org/abs/2106.09249) | 2021年 | IEEE S&P | Camera + LiDAR | 融合架构脆弱性 / 输入层攻击 | MSF-ADV | 通过可3D打印对象同时干扰相机与LiDAR，证明融合系统并非天然安全。 |
| [MAP: Multispectral Adversarial Patch to Attack Person Detection](https://scholar.google.com/scholar?q=MAP%3A%20Multispectral%20Adversarial%20Patch%20to%20Attack%20Person%20Detection) | 2022年 | IEEE ICASSP | Visible + Infrared | 输入层攻击 | MAP | 为可见光与红外双模态分别构造并对齐补丁，实现多光谱联合攻击。 |
| [Exploring Adversarial Robustness of Multi-sensor Perception Systems in Self Driving](https://proceedings.mlr.press/v164/tu22a.html) | 2022年 | CoRL / PMLR | Camera + LiDAR | 融合架构脆弱性 | Input-agnostic Adversarial Object | 研究输入无关、物理可实现的统一对抗物体，分析多传感器脆弱性。 |
| [Security Analysis of Camera-LiDAR Fusion against Black-box Attacks on Autonomous Vehicles](https://scholar.google.com/scholar?q=Security%20Analysis%20of%20Camera-LiDAR%20Fusion%20against%20Black-box%20Attacks%20on%20Autonomous%20Vehicles) | 2022年 | USENIX Security | Camera + LiDAR | 决策层攻击 / 黑盒分析 | Black-box Fusion Attack | 研究黑盒条件下相机-LiDAR融合系统的安全边界。 |
| [Multispectral Invisible Coating: Laminated Visible-Thermal Physical Attack against Multispectral Object Detectors Using Transparent Low-E Films](https://scholar.google.com/scholar?q=Multispectral%20Invisible%20Coating%3A%20Laminated%20Visible-Thermal%20Physical%20Attack%20against%20Multispectral%20Object%20Detectors%20Using%20Transparent%20Low-E%20Films) | 2023年 | AAAI | Visible + Infrared | 输入层攻击 | MIC | 利用透明Low-e薄膜的层压结构，把可见光纹理与热红外扰动集成到单一介质。 |
| [Unified Adversarial Patch for Cross-modal Attacks in the Physical World](https://openaccess.thecvf.com/content/ICCV2023/html/Wei_Unified_Adversarial_Patch_for_Cross-Modal_Attacks_in_the_Physical_World_ICCV_2023_paper.html) | 2023年 | CVPR | Visible + Infrared | 输入层攻击 | UAP | 设计统一补丁同时攻击可见光与红外模态。 |
| [Exploring Adversarial Robustness of LiDAR-camera Fusion Model in Autonomous Driving](https://scholar.google.com/scholar?q=Exploring%20Adversarial%20Robustness%20of%20LiDAR-camera%20Fusion%20Model%20in%20Autonomous%20Driving) | 2023年 | IEEE EI2 | Camera + LiDAR | 融合架构脆弱性 | LiDAR-Camera Fusion Robustness | 从实验角度评估LiDAR-相机融合模型的鲁棒性。 |
| [Two-stage Optimized Unified Adversarial Patch for Attacking Visible-Infrared Cross-modal Detectors in the Physical World](https://arxiv.org/abs/2401.09587) | 2024年 | arXiv / 2025刊发 | Visible + Infrared | 输入层攻击 | TOUAP | 分阶段优化形状与颜色编码，提高可见光-红外统一补丁的鲁棒性。 |
| [Fusion Is Not Enough: Single Modal Attacks on Fusion Models for 3D Object Detection](https://proceedings.iclr.cc/paper_files/paper/2024/hash/685d249ad59836727be209032f082bd7-Abstract-Conference.html) | 2024年 | ICLR | Camera + LiDAR | 特征层攻击 / 融合架构脆弱性 | Single-modal Attacks on Fusion | 指出仅攻击单一模态也能显著破坏融合3D检测，揭示融合架构的内在短板。 |
| [Evolutionary Multiobjective Cross-spectral Adversarial Attacks with Synergistic Patches](https://scholar.google.com/scholar?q=Evolutionary%20Multiobjective%20Cross-spectral%20Adversarial%20Attacks%20with%20Synergistic%20Patches) | 2025年 | IEEE TSMC | Visible + Infrared | 输入层攻击 | Synergistic Patches | 以多目标进化优化协同补丁，兼顾跨光谱攻击效果与物理约束。 |
| [CDUPatch: Color-driven Universal Adversarial Patch Attack for Dual-modal Visible-Infrared Detectors](https://arxiv.org/abs/2504.10888) | 2025年 | arXiv | Visible + Infrared | 输入层攻击 | CDUPatch | 基于颜色-热响应耦合关系，用颜色驱动统一纹理操控双模态成像。 |
| [Probing Vulnerabilities of Vision-LiDAR based Autonomous Driving Systems](https://scholar.google.com/scholar?q=Probing%20Vulnerabilities%20of%20Vision-LiDAR%20based%20Autonomous%20Driving%20Systems) | 2025年 | CVPR Workshops | Camera + LiDAR | 融合架构脆弱性 / 决策层分析 | Vision-LiDAR Vulnerability Probing | 系统分析视觉-LiDAR融合自动驾驶系统的脆弱点与攻击面。 |

---

## 防御策略

| 分类 | 含义说明 |
|---|---|
| 输入层预处理 | 指在样本进入模型前，通过压缩、滤波、重建、量化或随机变换等方式削弱扰动。其优点是可独立于具体模型部署，但对强攻击的适应性有限。 |
| 模型训练与结构增强 | 指通过对抗训练、蒸馏、去噪模块、鲁棒结构设计或可证明防御来提升模型本身的抗攻击能力。这类方法通常是提升鲁棒性的核心路线，但训练成本较高。 |
| 对抗检测与后处理校正 | 指先检测输入或局部区域是否异常，再进行掩码、抑制、修复或结果校正。该类方法更强调攻击识别与响应能力，适合作为补充防线。 |

| 论文题目 | 发表时间 | 出版社 | 所属分类 | 所提的方法名称 | 该方法的核心思想描述 |
|---|---:|---|---|---|---|
| [Explaining and Harnessing Adversarial Examples](https://arxiv.org/abs/1412.6572) | 2015年 | ICLR | 模型训练与结构增强 | FGSM / Adversarial Training | 提出FGSM，并奠定基于对抗样本训练提升鲁棒性的经典路线。 |
| [Distillation as a Defense to Adversarial Perturbations against Deep Neural Networks](https://ieeexplore.ieee.org/document/7546524) | 2016年 | IEEE S&P | 模型训练与结构增强 | Defensive Distillation | 通过蒸馏提升模型对扰动的平滑性与容错性。 |
| [Keeping the Bad Guys Out: Protecting and Vaccinating Deep Learning with JPEG Compression](https://arxiv.org/abs/1705.02900) | 2017年 | arXiv | 输入层预处理 | JPEG Compression | 用JPEG压缩实现轻量级输入净化与“疫苗式”防御。 |
| [Detecting Adversarial Samples from Artifacts](https://arxiv.org/abs/1703.00410) | 2017年 | arXiv | 对抗检测与后处理校正 | Artifact Detection | 利用统计伪影检测对抗样本。 |
| [Feature Squeezing: Detecting Adversarial Examples in Deep Neural Networks](https://evademl.org/docs/featuresqueezing.pdf) | 2018年 | NDSS | 输入层预处理 / 对抗检测与后处理校正 | Feature Squeezing | 通过量化、平滑等压缩输入表示，削弱对抗扰动并辅助检测。 |
| [Countering Adversarial Images Using Input Transformations](https://openreview.net/forum?id=SyJ7ClWCb) | 2018年 | ICLR | 输入层预处理 | Input Transformations | 通过JPEG压缩、量化、修复等输入变换破坏扰动结构。 |
| [Thermometer Encoding: One Hot Way to Resist Adversarial Examples](https://openreview.net/forum?id=S18Su--CW) | 2018年 | ICLR | 输入层预处理 | Thermometer Encoding | 对输入做离散编码，压缩连续可攻击空间。 |
| [Characterizing Adversarial Subspaces Using Local Intrinsic Dimensionality](https://openreview.net/forum?id=B1gJ1L2aW) | 2018年 | ICLR | 对抗检测与后处理校正 | LID Detection | 基于局部内在维度区分正常样本与对抗样本。 |
| [Towards Robust Detection of Adversarial Examples](https://papers.nips.cc/paper/2018/hash/b49704126e4b4e8d1050a8421beed0f6-Abstract.html) | 2018年 | NeurIPS | 对抗检测与后处理校正 | Robust Detection | 研究更稳定的对抗样本检测框架。 |
| [On Visible Adversarial Perturbations & Digital Watermarking](https://openaccess.thecvf.com/content_cvpr_2018_workshops/w16/html/Hayes_On_Visible_Adversarial_CVPR_2018_paper.html) | 2018年 | CVPR Workshops | 对抗检测与后处理校正 | Visible Perturbation Detection | 从可见扰动与数字水印角度分析检测思路。 |
| [Towards Deep Learning Models Resistant to Adversarial Attacks](https://openreview.net/forum?id=rJzIBfZAb) | 2018年 | ICLR | 模型训练与结构增强 | PGD Adversarial Training | 提出PGD对抗训练，成为后续鲁棒训练基线。 |
| [Local Gradients Smoothing: Defense against Localized Adversarial Attacks](https://openaccess.thecvf.com/content_WACV_2019/html/Naseer_Local_Gradients_Smoothing_Defense_Against_Localized_Adversarial_Attacks_WACV_2019_paper.html) | 2019年 | WACV | 输入层预处理 | LGS | 识别并平滑异常高梯度区域，抑制局部补丁类攻击。 |
| [Feature Denoising for Improving Adversarial Robustness](https://openaccess.thecvf.com/content_CVPR_2019/html/Xie_Feature_Denoising_for_Improving_Adversarial_Robustness_CVPR_2019_paper.html) | 2019年 | CVPR | 模型训练与结构增强 | Feature Denoising | 在特征层引入去噪模块，抑制对抗噪声传播。 |
| [Barrage of Random Transforms for Adversarially Robust Defense](https://openaccess.thecvf.com/content_CVPRW_2019/html/AT/barrage_of_random_transforms_for_adversarially_robust_defense.html) | 2019年 | CVPR Workshops | 输入层预处理 | Barrage | 组合多种随机变换，降低攻击的稳定性与可迁移性。 |
| [Theoretically Principled Trade-off between Robustness and Accuracy](https://proceedings.mlr.press/v97/zhang19p.html) | 2019年 | ICML | 模型训练与结构增强 | TRADES | 从理论上刻画鲁棒性与准确率权衡，并给出鲁棒训练目标。 |
| [Making an Invisibility Cloak: Real World Adversarial Attacks on Object Detectors](https://www.ecva.net/papers/eccv_2020/papers_ECCV/html/4389_ECCV_2020_paper.php) | 2020年 | ECCV | 模型训练与结构增强 | Adversarial Training for Cloak Attacks | 该文除攻击外也讨论了面向可穿戴/斗篷攻击的训练增强思路，因此综述在防御部分引用。 |
| [On the Convergence and Robustness of Adversarial Training](https://proceedings.mlr.press/v119/wang20k.html) | 2020年 | ICML | 模型训练与结构增强 | Adversarial Training Analysis | 分析对抗训练的优化收敛性与稳定性边界。 |
| [Adversarially Robust Distillation](https://ojs.aaai.org/index.php/AAAI/article/view/5760) | 2020年 | AAAI | 模型训练与结构增强 | ARD | 结合蒸馏与鲁棒训练目标，提升模型抗扰动能力。 |
| [Deep Distillation for Robust Learning](https://arxiv.org/abs/2010.11667) | 2020年 | arXiv | 模型训练与结构增强 | Deep Distillation | 通过教师-学生一致性提升鲁棒学习表现。 |
| [Clipped BagNet: Defending against Sticker Attacks with Clipped Bag-of-Features](https://ieeexplore.ieee.org/document/9370348) | 2020年 | IEEE S&P Workshops | 模型训练与结构增强 | Clipped BagNet | 通过受限局部特征聚合削弱贴纸攻击影响。 |
| [SentiNet: Detecting Localized Universal Attacks against Deep Learning Systems](https://ieeexplore.ieee.org/document/9370329) | 2020年 | IEEE S&P Workshops | 对抗检测与后处理校正 | SentiNet | 结合显著区域与泛化验证检测局部通用攻击。 |
| [Robust Knowledge Distillation for Adversarial Defense](https://ieeexplore.ieee.org/document/9449927) | 2021年 | IEEE Access | 模型训练与结构增强 | RKD | 将教师模型的鲁棒性迁移给轻量学生模型。 |
| [PatchGuard: A Provably Robust Defense against Adversarial Patches via Small Receptive Fields and Masking](https://www.usenix.org/conference/usenixsecurity21/presentation/xiang) | 2021年 | USENIX Security | 模型训练与结构增强 | PatchGuard | 用小感受野网络与掩码聚合提供对局部补丁的可证明防御。 |
| [PatchGuard++: Efficient Provable Attack Detection against Adversarial Patches](https://arxiv.org/abs/2104.12609) | 2021年 | arXiv | 对抗检测与后处理校正 | PatchGuard++ | 在PatchGuard基础上提升效率与检测能力。 |
| [DetectorGuard: Provably Securing Object Detectors against Localized Patch Hiding Attacks](https://dl.acm.org/doi/10.1145/3460120.3484573) | 2021年 | ACM CCS | 模型训练与结构增强 | DetectorGuard | 将可证明防御扩展到目标检测任务。 |
| [Efficient Certified Defenses against Patch Attacks on Image Classifiers](https://openaccess.thecvf.com/content/WACV2022/html/Metzen_Efficient_Certified_Defenses_Against_Patch_Attacks_on_Image_Classifiers_WACV_2022_paper.html) | 2022年 | WACV | 模型训练与结构增强 | Certified Patch Defense | 提供面向补丁攻击的高效认证式防御。 |
| [DIPDefend: Deep Image Prior Driven Defense against Adversarial Examples](https://openaccess.thecvf.com/content/CVPR2023W/WMF/html/Wang_DIPDefend_Deep_Image_Prior_Driven_Defense_Against_Adversarial_Examples_CVPRW_2023_paper.html) | 2023年 | CVPR Workshops | 输入层预处理 / 后处理校正 | DIPDefend | 借助深度图像先验重建自然图像，清除输入中的对抗扰动。 |
| [ObjectSeeker: Certifiably Robust Object Detection against Patch Hiding Attacks via Patch-agnostic Masking](https://ieeexplore.ieee.org/document/10179393) | 2023年 | IEEE S&P | 模型训练与结构增强 | ObjectSeeker | 通过与补丁无关的掩码策略实现检测器鲁棒认证。 |
| [Jujutsu: A Two-stage Defense against Adversarial Patch Attacks on Deep Neural Networks](https://dl.acm.org/doi/10.1145/3579856.3595802) | 2023年 | AsiaCCS | 对抗检测与后处理校正 | Jujutsu | 采用两阶段流程先检测再抑制补丁攻击。 |
| [Anomaly Unveiled: Securing Image Classification against Adversarial Patch Attacks](https://ieeexplore.ieee.org/document/10648161) | 2024年 | IEEE ICIP | 对抗检测与后处理校正 | Anomaly Unveiled | 基于局部异常统计识别补丁式攻击。 |
| [Model-agnostic Adversarial Example Detection via High-frequency Amplification](https://www.sciencedirect.com/science/article/pii/S0167404824001680) | 2024年 | Computers & Security | 对抗检测与后处理校正 | High-frequency Amplification | 放大高频特征差异，实现模型无关的对抗检测。 |

---

