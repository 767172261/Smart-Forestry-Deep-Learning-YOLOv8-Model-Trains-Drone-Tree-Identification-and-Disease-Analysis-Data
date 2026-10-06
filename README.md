

**---数据集文字描述：**

无人机树木识别及病害情况分析数据集
（松树、云杉树、白桦树、白杨树、其他树）
无人机：DJI 相机为FC200
数据类型：原始图片，已分类好的图片，打好的目标检测标签
总内存大小：6.57G（3501张）
图片分辨率：1536*1536
采集高度：30～60m
采集角度：90度，60度
树木类别：松树、云杉树、白桦树、白杨树、其他树
备注：树木损伤的类别分为两类：High Damage （HD） 和 Other。这些2类可单独可用于训练模型以进行损伤分类。在 331 张图像中，有 27,087 棵带注释的树木，其中 483 棵云杉树被注释有损坏。请注意，它们同时包含垂直和倾斜图像
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/63d995dc18b54786b45c7bfe34bfe554.png)

应用场景：用于应急，林业病害，低空目标检测等领域

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/75f08cd260e54546bcff9a7c320eafc9.png)

---
数据集文字描述：
### **无人机树木识别及病害分析数据集信息表**

| 项目 | 内容 |
|------|------|
| **数据集名称** | 无人机树木识别及病害情况分析数据集 |
| **总图像数量** | 3,501 张 |
| **总数据大小** | 6.57 GB |
| **图像分辨率** | 1536 × 1536 像素 |
| **采集设备** | DJI 无人机，搭载 FC200 相机 |
| **飞行高度** | 30～60 米 |
| **拍摄角度** | 垂直视角（90°）、倾斜视角（60°） |
| **数据类型** | 原始图片、已分类图片、目标检测标签（含边界框标注） |
| **标注格式** | 支持目标检测（如 YOLO `.txt` 或 VOC `.xml`，具体格式需确认） |
| **适用任务** | 树种分类、目标检测、树木健康状况（损伤）识别、病害监测 |

---
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/de675b82b1694a658297529ece574d85.png)

### **树木类别标签表**

| 类别编号 | 英文标签 | 中文名称 | 说明 |
|----------|-----------|------------|------|
| 0 | pine | 松树 | 针叶成束，树皮粗糙，常见于温带森林 |
| 1 | spruce | 云杉树 | 树冠尖塔形，针叶螺旋排列，耐寒性强 |
| 2 | birch | 白桦树 | 落叶乔木，树皮白色光滑，易识别 |
| 3 | aspen | 白杨树 | 叶片随风抖动，喜光，生长迅速 |
| 4 | other | 其他树 | 无法明确归类的树种 |

---

### **树木损伤类别标签表（可单独用于损伤分类任务）**

| 类别编号 | 英文标签 | 中文名称 | 说明 |
|----------|-----------|------------|------|
| 0 | HD | 高损伤（High Damage） | 树木出现严重枯死、断枝、大面积病害等视觉损伤 |
| 1 | other_damage | 其他（Other） | 轻微损伤或健康树木，作为对照组 |

> ✅ **特别说明**：  
> - 损伤类别可在 **331 张图像**中找到，共标注了 **27,087 棵树木**。  
> - 其中 **483 棵云杉树** 被明确标注为“高损伤”（HD）。  
> - 这些图像同时包含 **垂直（90°）和倾斜（60°）视角**，适合多视角建模研究。

---

### **数据集结构概览（推测）**

| 子集/文件夹 | 图像数量（约） | 主要内容 | 备注 |
|-------------|----------------|----------|------|
| `vertical/` | 待统计 | 垂直视角（90°）图像 | 包含树种与部分损伤标注 |
| `oblique/`  | 待统计 | 倾斜视角（60°）图像 | 包含树种与部分损伤标注 |
| `damage/`   | 331 张 | 含损伤标注的图像 | 同时包含垂直与倾斜图像，重点用于健康评估 |

---

### **数据集特点总结**

| 特点 | 说明 |
|------|------|
| ✅ **高分辨率成像** | 所有图像均为 1536×1536，细节丰富，利于小目标检测 |
| ✅ **双视角覆盖** | 包含 90° 垂直与 60° 倾斜视角，增强模型泛化能力 |
| ✅ **大规模标注** | 27,087 棵树木被精细标注，支持高精度目标检测 |
| ✅ **双任务支持** | 支持 **树种识别** 与 **树木健康状态（损伤）分类** 两大任务 |
| ✅ **真实场景数据** | 来源于真实林区航拍，包含遮挡、光照变化、复杂背景等现实挑战 |
| ✅ **可拆分使用** | 损伤子集（331 张）可独立用于二分类模型训练（HD vs Other） |

---

### **典型应用场景**

- 🌲 森林资源调查与树种分布制图  
- 🛰️ 无人机智能巡检系统  
- 🌿 林业病虫害、风灾、火灾后损伤评估  
- 📊 基于AI的生态健康监测平台  
- 🧠 多视角目标检测与分类算法研究

---

### **建议使用方式**

- 将完整数据集用于 **树种目标检测模型** 训练（如 YOLO、Faster R-CNN）；
- 使用 `damage` 子集训练 **树木健康分类模型**（HD vs Other），可作为图像分类或实例分类任务；
- 结合视角信息进行 **视角自适应模型** 或 **多模态融合** 研究。

---

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/6a4fa4f290bd4e1ba2d3fcc0f39bb9e4.png)



---
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/0829846b0355453f9ce9c5f2110b7fdf.png)
1
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/4a20c72524f949dab699cf995bd78286.png)
1
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/e460f70563b9432cba1935f2f948c082.png)
1
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/a51a47e4144e487d8b37deb03e05f15e.png)
1
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/d1f93fb9244b48cc94bc00b6ab80e48d.png)
 **无人机树木识别与病害分析数据集** ，具备高分辨率（1536×1536）、多角度（90° 垂直 + 60° 倾斜）、大样本量（27,087 棵树）和精细标注（含 HD 损伤），适合用于 **林业智能监测系统** 的开发。

我们将从 **环境搭建 → 数据处理 → 模型训练 → 推理评估** 全流程指导**YOLOv8** 实现：

✅ 树木种类检测（松树、云杉、白桦、白杨、其他）  
✅ 树木损伤识别（High Damage / Other）  
✅ 支持多视角融合训练  
✅ 提供完整训练/推理/评估代码

---

## 🌲 一、数据集关键信息总结

| 项目 | 内容 |
|------|------|
| 图像数量 | 3501 张 |
| 分辨率 | 1536 × 1536 |
| 采集设备 | DJI FC200 相机 |
| 采集高度 | 30～60m |
| 采集角度 | 90°（垂直） + 60°（倾斜） |
| 树木总数 | 27,087 棵 |
| 树种类别 | 松树、云杉、白桦、白杨、其他树 |
| 损伤类别 | High Damage (HD) / Other（共 483 棵 HD 云杉） |
| 数据格式 | 原始图像 + 已分类图像 + 目标检测标签（推测为 `.xml` 或 `.txt`） |
| 存储大小 | 6.57 GB |



---

## 🧰 二、环境搭建（CUDA + Conda + YOLOv8）

### 1. 检查 CUDA 驱动

```bash
nvidia-smi
```

- 确保显示驱动版本和 GPU（如 RTX 3090/4090/A6000）
- 推荐 CUDA 11.8 或 12.1

---

### 2. 安装 Anaconda

官网下载：[https://www.anaconda.com/products/distribution](https://www.anaconda.com/products/distribution)

---

### 3. 创建 Python 虚拟环境

```bash
conda create -n tree_ai python=3.9
conda activate tree_ai
```

---

### 4. 安装依赖项

```bash
# 安装 PyTorch（以 CUDA 11.8 为例）
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

# 安装 Ultralytics YOLOv8
pip install ultralytics

# 安装其他工具
pip install opencv-python numpy matplotlib lxml scikit-learn tqdm pillow
```

✅ 验证安装：

```python
import torch
print(torch.__version__)
print(torch.cuda.is_available())  # 应输出 True
```

---

## 📂 三、数据结构假设与格式转换

由于你提到“已分类图片”和“打好的标签”，我们假设数据结构如下：

```
dataset/
├── images/
│   ├── vertical/
│   ├── oblique/
│   └── damage/
├── labels_xml/  # 或 annotations/
│   ├── vertical/
│   ├── oblique/
│   └── damage/
```

### ✅ 目标：将 `.xml`（VOC 格式）转换为 YOLO 格式 `.txt`

```python
# convert_voc_to_yolo.py
import os
import xml.etree.ElementTree as ET
from pathlib import Path
import shutil

# 类别定义
species_classes = ['pine', 'spruce', 'birch', 'aspen', 'other']
damage_classes = ['no_damage', 'high_damage']  # 我们将 HD 视为一种状态

species_to_id = {cls: idx for idx, cls in enumerate(species_classes)}
# damage_to_id = {cls: idx for idx, cls in enumerate(damage_classes)}

def convert_box(size, box):
    dw = 1. / size[0]
    dh = 1. / size[1]
    x = (box[0] + box[1]) / 2.0
    y = (box[2] + box[3]) / 2.0
    w = box[1] - box[0]
    h = box[3] - box[2]
    return x * dw, y * dh, w * dw, h * dh

def parse_label(name: str):
    name = name.lower().strip()
    # 判断树种
    species = None
    is_hd = False

    if 'pine' in name:
        species = 'pine'
    elif 'spruce' in name:
        species = 'spruce'
    elif 'birch' in name:
        species = 'birch'
    elif 'aspen' in name:
        species = 'aspen'
    elif 'other' in name:
        species = 'other'

    if 'hd' in name or 'high_damage' in name or 'damage' in name:
        is_hd = True

    return species, is_hd

def convert_all_annotations(img_dir_root, xml_dir_root, output_img_dir, output_label_dir):
    os.makedirs(output_img_dir, exist_ok=True)
    os.makedirs(output_label_dir, exist_ok=True)

    total_converted = 0

    for split in ['vertical', 'oblique', 'damage']:
        img_dir = Path(os.path.join(img_dir_root, split))
        xml_dir = Path(os.path.join(xml_dir_root, split))

        if not img_dir.exists() or not xml_dir.exists():
            continue

        for xml_file in xml_dir.glob("*.xml"):
            tree = ET.parse(xml_file)
            root = tree.getroot()
            size = root.find('size')
            if size is None: continue
            w = int(size.find('width').text)
            h = int(size.find('height').text)

            image_name = xml_file.stem + '.jpg'
            src_img = img_dir / image_name
            dst_img = Path(output_img_dir) / image_name

            if src_img.exists():
                shutil.copy(src_img, dst_img)  # 复制图像

            lines = []
            for obj in root.findall('object'):
                label_name = obj.find('name').text
                species, is_hd = parse_label(label_name)

                if not species:
                    continue

                bbox = obj.find('bndbox')
                xmin = float(bbox.find('xmin').text)
                ymin = float(bbox.find('ymin').text)
                xmax = float(bbox.find('xmax').text)
                ymax = float(bbox.find('ymax').text)
                bb = convert_box((w, h), (xmin, xmax, ymin, ymax))

                # 写入树种标签
                lines.append(f"{species_to_id[species]} {' '.join(f'{x:.6f}' for x in bb)}")

            # 保存 .txt 标签
            with open(Path(output_label_dir) / (xml_file.stem + '.txt'), 'w') as f:
                f.write('\n'.join(lines))

            total_converted += 1

    print(f"✅ 成功转换 {total_converted} 个文件")

# 路径配置（请根据实际路径修改）
convert_all_annotations(
    img_dir_root="dataset/images",
    xml_dir_root="dataset/labels_xml",
    output_img_dir="yolo_dataset/images/all",
    output_label_dir="yolo_dataset/labels/all"
)
```

---

## 📄 四、创建 `data.yaml` 配置文件

### 4.1 树种检测配置文件

```yaml
# species.yaml
train: yolo_dataset/images/all
val: yolo_dataset/images/all  # 后续可划分验证集
test: yolo_dataset/images/all

nc: 5
names: ['pine', 'spruce', 'birch', 'aspen', 'other']
```

### 4.2 损伤检测配置文件（可选）

如果你只想检测 HD 树木，可单独训练：

```yaml
# damage.yaml
train: yolo_dataset/images/damage_only
val: ...
nc: 2
names: ['healthy', 'high_damage']
```

---

## 🔁 五、划分训练/验证集（推荐）

```python
# split_dataset.py
import os
from sklearn.model_selection import train_test_split
from glob import glob

all_images = glob("yolo_dataset/images/all/*.jpg")
image_names = [os.path.basename(img) for img in all_images]

train_names, test_names = train_test_split(image_names, test_size=0.2, random_state=42)
val_names, test_names = train_test_split(test_names, test_size=0.5, random_state=42)

def write_list(names, path):
    with open(path, 'w') as f:
        f.write('\n'.join(names))

write_list(train_names, "yolo_dataset/train.txt")
write_list(val_names, "yolo_dataset/val.txt")
write_list(test_names, "yolo_dataset/test.txt")

print("✅ 数据集划分完成")
```

修改 `species.yaml` 中的路径：

```yaml
train: yolo_dataset/train.txt
val: yolo_dataset/val.txt
```

---

## 🚀 六、训练模型（YOLOv8）

### 6.1 训练代码（`train.py`）

```python
# train.py
from ultralytics import YOLO

# 加载预训练模型（推荐使用 m 或 l 版本）
model = YOLO('yolov8m.pt')  # 或 yolov8l.pt 提升精度

# 开始训练
results = model.train(
    data='species.yaml',
    epochs=150,
    imgsz=1536,           # 使用原始分辨率
    batch=8,              # 根据 GPU 显存调整（A6000 可用 16）
    name='tree_detection',
    project='runs/trees',
    device=0,             # 使用 GPU
    workers=4,
    optimizer='AdamW',
    lr0=0.001,
    patience=20,          # 早停
    augment=True,         # 启用 Mosaic、MixUp 等增强
    close_mosaic=15,      # 最后15轮关闭 Mosaic
    cache='disk'          # 缓存图像到磁盘，加速训练
)

print("✅ 训练完成！")
```

> 📌 模型保存路径：`runs/trees/tree_detection/weights/best.pt`

---

## 🔍 七、推理与预测代码（`infer.py`）

```python
# infer.py
from ultralytics import YOLO
import cv2

# 加载模型
model = YOLO('runs/trees/tree_detection/weights/best.pt')

# 单张图像推理
results = model('test.jpg', conf=0.4, iou=0.5)

# 显示结果
for r in results:
    im_array = r.plot()  # 绘制边界框和标签
    im = cv2.cvtColor(im_array, cv2.COLOR_RGB2BGR)
    cv2.imshow('Tree Detection', im)
    cv2.waitKey(0)
    cv2.imwrite('result.jpg', im)

# 批量推理
results = model('yolo_dataset/images/all/', save=True, project='runs/predict', name='tree_results')
```

---

## 📊 八、评估模型性能（`evaluate.py`）

```python
# evaluate.py
from ultralytics import YOLO

model = YOLO('runs/trees/tree_detection/weights/best.pt')

# 在验证集上评估
metrics = model.val(
    data='species.yaml',
    split='val',
    batch=8,
    imgsz=1536,
    device=0,
    save_json=True  # 生成 COCO 格式结果
)

# 输出关键指标
print(f"mAP@50: {metrics.box.map50:.4f}")
print(f"mAP@50-95: {metrics.box.map:.4f}")
print(f"Precision: {metrics.box.p:.4f}")
print(f"Recall: {metrics.box.r:.4f}")

# 混淆矩阵保存在 runs/val/ 目录下
```

---

## 📈 九、性能优化建议

| 问题 | 建议 |
|------|------|
| 显存不足 | 使用 `imgsz=1280` 或 `yolov8n`，或启用 `--half` 半精度 |
| 小树难检测 | 使用 `mosaic=1.0`，`scale=0.9`，`hsv_h=0.015` 增强 |
| 多角度差异大 | 数据增强中加入旋转、仿射、透视变换 |
| 损伤样本少 | 对 HD 样本进行过采样或使用 Focal Loss |
| 推理慢 | 导出为 ONNX 或 TensorRT 加速 |

---

## 🔄 十、模型导出（用于部署）

```python
# export.py
from ultralytics import YOLO

model = YOLO('runs/trees/tree_detection/weights/best.pt')
model.export(
    format='onnx',
    dynamic=True,
    simplify=True,
    imgsz=1536
)
print("✅ 已导出为 ONNX 模型")
```

以上文字及代码仅供参考学习使用。
