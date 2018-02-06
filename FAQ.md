1. Matrix API
===
1.1 MatrixOperFunctor
---
##1.1.1 Interface##
[MATRIX_StatusT](http://www.baidu.com) MATRIX_StatusT MatrixOperFunctor::[Init](#1)(const AIConfig& config, const vector<AIModelDescription>& model_desc) 
初始化写操作的参数.
MATRIX_StatusT Destroy(const AIConfig& config) 
实现自定义写操作.
MATRIX_StatusT MatrixWriteInterface::GetOperDescriptor(AIOPDescription& desc) = 0
获取该Op操作的描述符.

##1.1.2 function##
<h4 id="1">`MatrixOperFunctor::Init`</h4>
    Parameters
        Config
            - OP操作所需要的参数以key/value形式传递
    
    Returns
        参见enum MATRIX_StatusT定义
        
    Description
        用户通过实现该纯虚函数，完成对自定义写操作的初始化，例如，用户可以设置写入的路径等。
        
    MATRIX_StatusT MatrixWriteInterface::Write(vector<shared_ptr<IAITensor>> msg_input,AIContext& context)
    
    Parameters
        msg_input
            - 待处理的结果内容.
        
        context
            - reserved，保留.用户实现Write函数时，不需要关心该参数.
    
    Returns
        参见enum MATRIX_StatusT定义
        
    Description
        用户通过实现该纯虚函数，完成对自定义写操作的具体实现，例如，用户可以实现写文件的具体操作方式.
        
    MATRIX_StatusT MatrixWriteInterface::GetOperDescriptor(AIOPDescription& desc)
    
    Parameters
        desc
            - 该操作的描述符.例如，该操作接受的输入内容的格式.
    
    Returns
        参见enum MATRIX_StatusT定义
        
    Description
        用户通过实现该纯虚函数，提供该操作接受的输入内容的格式.在判断前后两个节点是否可以连接时使用.





[TOC]
