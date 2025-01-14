# Spec 构建的匹配树
```python
eg: dict = {
    "type": SpecType.general,  # anyType / generalType / noneType
    "value": {
        "input": {
            "type": dict,
            "required": True,
            "next": {
                "type": SpecType.any, 
                "value": {
                    "__any__": {
                        "type": dict,
                        "required": True,
                        "next": {
                            "type": SpecType.general,
                            "value": {
                                "src": {
                                    "type": str,
                                    "required": True,
                                    "next": {
                                        "type": SpecType.none
                                    }
                                },
                                "depends":{
                                    "type": str,
                                    "required": True,
                                    "next": {
                                        "type": SpecType.general
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
    },
}
```