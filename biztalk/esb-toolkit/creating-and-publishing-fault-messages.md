---
title: "Creación y publicación de mensajes de error | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc7ba1d9-b647-4cba-a3dc-4400505ff51f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57833cefedcf53b7355c17cf97d429d2eb988819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-publishing-fault-messages"></a>Creación y publicación de mensajes de error
Para ayudarle a entender cómo utilizar las características del marco de administración de excepciones para administrar excepciones, esta sección presenta un escenario común que se basa en el envío de un mensaje a una aplicación de ESB.  
  
 El escenario consta de un usuario que se envía una factura para el sistema. En el transcurso de la factura en una orquestación de procesamiento, el motor de reglas de negocio de BizTalk produce una excepción de aplicación porque alguna parte de los datos es incorrecto. El proceso empresarial debe detectar la excepción, enviar el mensaje infractor a otra persona o sistema que puede corregir el mensaje y, a continuación, vuelva a enviar el mensaje para su procesamiento.  
  
 Al utilizar la característica excepción enrutamiento de orquestación de error de ESB, los pasos del proceso son los siguientes:  
  
1.  Detecta el error de código en el controlador de excepciones y crea un mensaje de error mediante una llamada a la **CreateFaultMessage** método, tal como se muestra en el ejemplo de código siguiente.  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  El mecanismo de excepciones de ESB inserta automáticamente la descripción del error en el contexto del mensaje de error (por ejemplo, "el motor de reglas de negocios produjo una división por cero error al procesar la directiva LoanProcessing.").  
  
3.  El mecanismo de excepciones de ESB automáticamente promociona propiedades específicas del error y propiedades específicos de la aplicación en el contexto del mensaje de error y establece los valores del entorno actual. Estas propiedades son los siguientes:  
  
    -   **Aplicación** (rellena automáticamente)  
  
    -   **Fecha y hora** (rellena automáticamente como un valor de hora UTC)  
  
    -   **Descripción** (rellena automáticamente, el mensaje de excepción)  
  
    -   **ErrorType** (rellena automáticamente: el tipo de excepción)  
  
    -   **MachineName** (rellena automáticamente, el nombre del servidor actual)  
  
    -   **Ámbito** (rellena automáticamente, la forma de ámbito que contiene el controlador de excepción actual)  
  
    -   **ServiceName** (rellena automáticamente, el nombre de la orquestación)  
  
    -   **ServiceInstanceID**(rellena automáticamente: el identificador de instancia de orquestación como un GUID)  
  
4.  Código en el controlador de excepción establece otras propiedades del mensaje de error según sea necesario, como se muestra en el ejemplo de código siguiente.  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  El mecanismo de excepciones de ESB serializa automáticamente actual **excepción** objeto en el mensaje de error.  
  
6.  Si lo desea, el código en el controlador de excepciones puede agregar mensajes de orquestación actual con el mensaje de error ESB utilizando la **AddMessage (faultMsg, messageToAdd)** método. Este método serializa y envía el mensaje, incluidas todas las propiedades de contexto, como se muestra en el ejemplo de código siguiente.  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  Código en el controlador de excepciones, publica el mensaje de error ESB en la base de datos de cuadro de mensaje con un puerto de enlace directo.  
  
8.  Si la publicación se realiza correctamente, se producen los siguientes eventos:  
  
    -   Las suscripciones de puerto de orquestación o envío pueden procesar el mensaje de error ESB y extraer los mensajes agregados, junto con sus valores de propiedad de contexto.  
  
    -   Un controlador de excepciones global (un puerto de envío) publica automáticamente el mensaje de error ESB en el Portal de administración de ESB.