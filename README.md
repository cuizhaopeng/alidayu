# alidayu
PS：阿里短信 https://github.com/cuizhaopeng/alidayu

**更新**
暂无

**功能**
短信发送

**环境**
PHP >= 5.4
composer

**使用**

示例：

class SendMessage{

    public function sendPhoneMessage(){
    
        // *** 需用户填写部分 ***

        // fixme 必填: 请参阅 https://ak-console.aliyun.com/ 取得您的AK信息
        $accessKeyId = "LTAIp75FRoFjEUf2";
        $accessKeySecret = "8tEQ1bakjiFudJTzW3D2skHGlJEW6j";
        // fixme 必填: 短信接收号码
        $params["PhoneNumbers"] = $_POST['phone_numbers'];

        // fixme 必填: 短信签名，应严格按"签名名称"填写，请参考: https://dysms.console.aliyun.com/dysms.htm#/develop/sign
        $params["SignName"] = "短信签名";

        // fixme 必填: 短信模板Code，应严格按"模板CODE"填写, 请参考: https://dysms.console.aliyun.com/dysms.htm#/develop/template
        $params["TemplateCode"] = "SMS_142946435";

        // fixme 可选: 设置模板参数, 假如模板中存在变量需要替换则为必填项
        $params['TemplateParam'] = Array (
            "username" => $_POST['username'],
            "post" => $_POST['post'],
            "invitation_time" => $_POST['invitation_time']
        );

        $sendSms = new sendSms();
        $res = $sendSms->send($accessKeyId,$accessKeySecret,$params);
        return $res;
    }
} 

**帮助**

意见、BUG反馈： https://github.com/cuizhaopeng/alidayu/issues

**支持**

官方网址： https://www.alidayu.com/

官方API文档： https://api.alidayu.com/doc2/apiList.htm

composer： https://getcomposer.org/

**License**

MIT