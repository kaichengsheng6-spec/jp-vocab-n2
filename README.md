# 📚 日语词汇表 / Japanese Vocabulary Site

基于《新标准日本语》中级词汇整理的在线学习网站，支持发音、例句与收藏功能。

**在线访问 →** https://kaichengsheng6-spec.github.io/jp-vocab-n2

---

## 功能特性

| 功能 | 说明 |
|------|------|
| 🔍 实时搜索 | 按假名、日文、中文意思搜索 |
| 🏷️ 词性筛选 | 名词 / 动词 / 形容词 / 副词 / 惯用语等 |
| 🔊 单词发音 | 每个词条均有真人语音（Edge-TTS，女声标准东京口音） |
| 📖 例句 | AI 生成自然例句（N3-N4 难度），含汉字振假名标注 |
| 🔊 例句发音 | 例句整句朗读 |
| 🔖 书签 | 设置单个书签，一键跳转到学习位置 |
| ⭐ 收藏 | 收藏单词，在新标签页查看，支持打印 / 导出 PDF |

---

## 数据来源

- 词汇：《新标准日本语》中级（约 3300 词，排除专有词）
- 发音：[Microsoft Edge TTS](https://github.com/rany2/edge-tts)（`ja-JP-NanamiNeural`）
- 例句：本地 Qwen3.5-397B 大语言模型生成

---

## 技术栈

```
Python          数据处理 / 自动化流程
edge-tts        日语 TTS 语音合成
Qwen3.5-397B    例句生成（本地推理）
openpyxl        Excel 读取
原生 HTML/CSS/JS 前端（无框架，单文件）
```

---

## 本地开发

```bash
# 安装依赖
pip install edge-tts openpyxl requests

# 生成分类词汇表（Excel）
python utils/classify_words.py

# 生成单词发音 MP3
python utils/gen_audio.py

# 生成例句（需要本地大模型）
python utils/gen_examples.py

# 生成例句发音 MP3
python utils/gen_audio_ex.py

# 构建网页
python utils/build_web.py

# 本地预览
cd web && python -m http.server 8080
# 访问 http://localhost:8080
```
