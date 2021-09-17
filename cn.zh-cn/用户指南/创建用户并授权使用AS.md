# 创建用户并授权使用AS<a name="as_07_0102"></a>

## 操作场景<a name="section2495449014355"></a>

如果您需要对您所拥有的AS进行精细的权限管理，您可以使用[统一身份认证服务](https://support.huaweicloud.com/usermanual-iam/iam_01_0001.html)（Identity and Access Management，简称IAM），通过IAM，您可以：

-   根据企业的业务组织，在您的华为云帐号中，给企业中不同职能部门的员工创建IAM用户，让员工拥有唯一安全凭证，并使用AS资源。
-   根据企业用户的职能，设置不同的访问权限，以达到用户之间的权限隔离。
-   [统一身份认证服务](https://support.huaweicloud.com/usermanual-iam/iam_01_0001.html)将AS资源委托给更专业、高效的其他华为云帐号或者云服务，这些帐号或者云服务可以根据权限进行代运维。

如果华为云帐号已经能满足您的要求，不需要创建独立的IAM用户，您可以跳过本章节，不影响您使用AS服务的其它功能。

本章节为您介绍对用户授权的方法，操作流程如[图1](#fig1515164216142)所示。

## 前提条件<a name="section6126111243014"></a>

给用户组授权之前，请您了解用户组可以添加的AS系统权限，并结合实际需求进行选择，AS支持的系统权限，请参见：[AS系统权限](https://support.huaweicloud.com/productdesc-as/as_pro_0007.html)。若您需要对除AS之外的其它服务授权，IAM支持服务的所有策略请参见[系统权限](https://support.huaweicloud.com/usermanual-permissions/zh-cn_topic_0063498930.html)。

## 示例流程<a name="section203711514125317"></a>

**图 1**  给用户授权AS权限流程<a name="fig1515164216142"></a>  
![](figures/给用户授权AS权限流程.jpg "给用户授权AS权限流程")

1.  <a name="li10176121316284"></a>[创建用户组并授权](https://support.huaweicloud.com/usermanual-iam/iam_03_0001.html)

    在IAM控制台创建用户组，并授予弹性伸缩权限“AutoScaling ReadOnlyAccess”。

2.  [创建用户并加入用户组](https://support.huaweicloud.com/usermanual-iam/iam_02_0001.html)

    在IAM控制台创建用户，并将其加入[1](#li10176121316284)中创建的用户组。

3.  [用户登录](https://support.huaweicloud.com/usermanual-iam/iam_01_0552.html)并验证权限

    新创建的用户登录控制台，切换至授权区域，验证权限：

    -   在“服务列表”中选择弹性伸缩服务，进入AS主界面，单击右上角“创建伸缩组”，如果无法创建伸缩组（假设当前权限仅包含AutoScaling ReadOnlyAccess），表示“AutoScaling ReadOnlyAccess”已生效。
    -   在“服务列表”中选择除弹性伸缩服务外（假设当前策略仅包含ECS Viewer）的任一服务，若提示权限不足，表示“AutoScaling ReadOnlyAccess”已生效。


