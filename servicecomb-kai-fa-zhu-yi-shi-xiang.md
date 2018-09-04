## 关于OpenAPI文档中require属性的成员变量

采用注解@NotNull

```java
import javax.validation.constraints.NotNull;

public class UeContextTransferReqData {
    @NotNull
    TransferReason reason; //indicate the reason for the UEContextTransfer service request "INIT_REG","MOBI_REG","MOBI_REG_UE_VALIDATED"
    N1MessageContainer regRequest; // if present, the IE shall refer to the registration request message which triggers the UE Context Transfer.
                                   // the message class shall be "5GMM" and
                                   // message content shall be reference to N1 Message Content binary data
    String supportedFeatures;

    public UeContextTransferReqData() {
    }

    public UeContextTransferReqData(TransferReason reason) {
        super();
        this.reason = reason;
    }
    public TransferReason getReason() {
        return reason;
    }
    public void setReason(TransferReason reason) {
        this.reason = reason;
    }
    public N1MessageContainer getRegRequest() {
        return regRequest;
    }
    public void setRegRequest(N1MessageContainer regRequest) {
        this.regRequest = regRequest;
    }
    public String getSupportedFeatures() {
        return supportedFeatures;
    }
    public void setSupportedFeatures(String supportedFeatures) {
        this.supportedFeatures = supportedFeatures;
    }

}
```

对应生成的契约为：

```OpenAPI
UeContextTransferReqData:
    type: "object"
    required:
    - "reason"
    properties:
      reason:
        type: "string"
        enum:
        - "INIT_REG"
        - "MOBI_REG"
        - "MOBI_REG_UE_VALIDATED"
        x-java-class: "DateModel.TransferReason"
      regRequest:
        $ref: "#/definitions/N1MessageContainer"
      supportedFeatures:
        type: "string"
    x-java-class: "DateModel.UeContextTransferReqData"
```

## 每个DataModel都要创建空的构造方法

> 因为我们的DataModel大部分都显示地定义了构造方法，

## Response  Body 的各类实现

> 正常的返回采用return 返回需要的Data Type
>
> 错误的返回 采用抛出异常的方式来处理 参考 [https://docs.servicecomb.io/java-chassis/zh\_CN/general-development/error-handling.html](https://docs.servicecomb.io/java-chassis/zh_CN/general-development/error-handling.html "异常处理") 来实现



