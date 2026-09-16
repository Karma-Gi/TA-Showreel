# TA Showreel｜技术美术作品集

基于 Unity URP 的实时材质与着色作品，涵盖 PBR／IBL、各向异性金属和程序化水体。以下为带中文说明的实机录制。

## 01 · PBR／IBL 着色与参数化材质开发

**[观看／下载演示视频（MP4，约 12 MiB）](https://github.com/Karma-Gi/TA-Showreel/releases/download/showreel-v1/PBR_IBL_portfolio_zh_with_overview.mp4)**

以九球展示金、银、铜、凹凸、条纹及金属／非金属混合等材质，呈现不同表面参数下的高光、质感与环境反射。

- 编写 Cook–Torrance PBR Shader，结合 Unity 球谐漫反射与预过滤反射探针构建直接光和 IBL 光照。
- 使用 Compute Shader、Hammersley 序列及 GGX 重要性采样烘焙 BRDF LUT，接入 Split-Sum 镜面 IBL；扩展各向异性高光及环境反射方向近似。
- 通过高度纹理三平面采样、差分凹凸法线、程序化条纹与金属遮罩，提供可调节的材质表现。

## 02 · 程序化水纹材质开发与 Water Elemental 模型应用

**[观看／下载演示视频（MP4，约 196 MiB）](https://github.com/Karma-Gi/TA-Showreel/releases/download/showreel-v1/Water_portfolio_zh_front_orbit.mp4)**

将程序化水纹应用于 Meshy 生成的水元素模型，通过正面与环绕镜头展示流动水纹、反射、透射和水体厚度变化。

- 结合多尺度噪声、三平面映射、双相位流动混合与差分法线重建生成动态水纹，并缓存噪声纹理供运行时采样。
- 沿模型 3D SDF 步进定位出射点，计算入射／出射折射和内部路径长度，以环境探针近似透射背景。
- 结合 Cook–Torrance 高光、Fresnel 环境反射、Beer–Lambert 吸收及双瓣 Henyey–Greenstein 散射近似表现水体质感；通过 SDF 烘焙与材质参数同步适配不同 Mesh。

## 视频与资产说明

- 两段原始 MP4 保存在 [Releases](https://github.com/Karma-Gi/TA-Showreel/releases/tag/showreel-v1)，点击上述链接可打开或下载，具体行为取决于浏览器。
- 本仓库用于作品展示；水元素模型由 Meshy 生成，个人工作聚焦材质开发、渲染效果与资产适配。
- 展示所用技术：Unity URP、HLSL、C#、Compute Shader、RenderTexture、3D SDF。
