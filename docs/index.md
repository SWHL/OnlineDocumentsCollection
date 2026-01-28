---
comments: true
---

本项目旨在收集散落在互联网的优秀帖子，主题不限。

!!! note

    这是测试

<div class="grid" markdown>
    config.yaml部分参数示例：
    ```yaml linenums="1"
    Det:
        engine_type: 'openvino'
        lang_type: 'ch'
        model_type: 'mobile'
        ocr_version: 'PP-OCRv4'

    EngineConfig:
        torch:
            use_cuda: false
            cuda_ep_cfg:
                device_id: 0
    ```

    对应参数写法
    ```python linenums="1" hl_lines="5-10"
    from rapidocr import EngineType, LangDet, ModelType, OCRVersion, RapidOCR

    engine = RapidOCR(
        params={
            "Det.engine_type": EngineType.TORCH,
            "Det.lang_type": LangDet.CH,
            "Det.model_type": ModelType.MOBILE,
            "Det.ocr_version": OCRVersion.PPOCRV5,
            "EngineConfig.torch.use_cuda": True,  # 使用torch GPU版推理
            "EngineConfig.torch.cuda_ep_cfg.device_id": 0,  # 指定GPU id
        }
    )
    ```

</div>
