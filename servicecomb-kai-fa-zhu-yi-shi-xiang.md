## 关于OpenAPI文档中require属性的成员变量

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



