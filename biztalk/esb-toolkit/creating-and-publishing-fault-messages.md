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
# <a name="creating-and-publishing-fault-messages"></a><span data-ttu-id="2cce9-102">Creación y publicación de mensajes de error</span><span class="sxs-lookup"><span data-stu-id="2cce9-102">Creating and Publishing Fault Messages</span></span>
<span data-ttu-id="2cce9-103">Para ayudarle a entender cómo utilizar las características del marco de administración de excepciones para administrar excepciones, esta sección presenta un escenario común que se basa en el envío de un mensaje a una aplicación de ESB.</span><span class="sxs-lookup"><span data-stu-id="2cce9-103">To help you understand how to use the features of the Exception Management Framework to manage exceptions, this section presents a common scenario based on the submission of a message to an ESB application.</span></span>  
  
 <span data-ttu-id="2cce9-104">El escenario consta de un usuario que se envía una factura para el sistema.</span><span class="sxs-lookup"><span data-stu-id="2cce9-104">The scenario consists of a user submitting an invoice to the system.</span></span> <span data-ttu-id="2cce9-105">En el transcurso de la factura en una orquestación de procesamiento, el motor de reglas de negocio de BizTalk produce una excepción de aplicación porque alguna parte de los datos es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="2cce9-105">During the course of processing the invoice in an orchestration, the BizTalk Business Rules Engine throws an application exception because some part of the data is incorrect.</span></span> <span data-ttu-id="2cce9-106">El proceso empresarial debe detectar la excepción, enviar el mensaje infractor a otra persona o sistema que puede corregir el mensaje y, a continuación, vuelva a enviar el mensaje para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2cce9-106">The business process should catch the exception, send the offending message to another person or system that can correct the message, and then resubmit the message for processing.</span></span>  
  
 <span data-ttu-id="2cce9-107">Al utilizar la característica excepción enrutamiento de orquestación de error de ESB, los pasos del proceso son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2cce9-107">When using the ESB Failed Orchestration Exception Routing feature, the process steps are the following:</span></span>  
  
1.  <span data-ttu-id="2cce9-108">Detecta el error de código en el controlador de excepciones y crea un mensaje de error mediante una llamada a la **CreateFaultMessage** método, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2cce9-108">Code in the exception handler detects the error and creates a fault message by calling the **CreateFaultMessage** method, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  <span data-ttu-id="2cce9-109">El mecanismo de excepciones de ESB inserta automáticamente la descripción del error en el contexto del mensaje de error (por ejemplo, "el motor de reglas de negocios produjo una división por cero error al procesar la directiva LoanProcessing.").</span><span class="sxs-lookup"><span data-stu-id="2cce9-109">The ESB Exception mechanism automatically inserts the error description into the fault message context (for example, "The Business Rules Engine threw a divide by zero error while processing the LoanProcessing policy.").</span></span>  
  
3.  <span data-ttu-id="2cce9-110">El mecanismo de excepciones de ESB automáticamente promociona propiedades específicas del error y propiedades específicos de la aplicación en el contexto del mensaje de error y establece los valores del entorno actual.</span><span class="sxs-lookup"><span data-stu-id="2cce9-110">The ESB Exception mechanism automatically promotes failure-specific properties and application-specific properties into the fault message context and sets the values from the current environment.</span></span> <span data-ttu-id="2cce9-111">Estas propiedades son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2cce9-111">These properties are the following:</span></span>  
  
    -   <span data-ttu-id="2cce9-112">**Aplicación** (rellena automáticamente)</span><span class="sxs-lookup"><span data-stu-id="2cce9-112">**Application** (auto-populated)</span></span>  
  
    -   <span data-ttu-id="2cce9-113">**Fecha y hora** (rellena automáticamente como un valor de hora UTC)</span><span class="sxs-lookup"><span data-stu-id="2cce9-113">**DateTime** (auto-populated as a UTC value)</span></span>  
  
    -   <span data-ttu-id="2cce9-114">**Descripción** (rellena automáticamente, el mensaje de excepción)</span><span class="sxs-lookup"><span data-stu-id="2cce9-114">**Description** (auto-populated—the exception message)</span></span>  
  
    -   <span data-ttu-id="2cce9-115">**ErrorType** (rellena automáticamente: el tipo de excepción)</span><span class="sxs-lookup"><span data-stu-id="2cce9-115">**ErrorType** (auto-populated—the exception type)</span></span>  
  
    -   <span data-ttu-id="2cce9-116">**MachineName** (rellena automáticamente, el nombre del servidor actual)</span><span class="sxs-lookup"><span data-stu-id="2cce9-116">**MachineName** (auto-populated—the current server name)</span></span>  
  
    -   <span data-ttu-id="2cce9-117">**Ámbito** (rellena automáticamente, la forma de ámbito que contiene el controlador de excepción actual)</span><span class="sxs-lookup"><span data-stu-id="2cce9-117">**Scope** (auto-populated—the Scope shape that contains the current exception handler)</span></span>  
  
    -   <span data-ttu-id="2cce9-118">**ServiceName** (rellena automáticamente, el nombre de la orquestación)</span><span class="sxs-lookup"><span data-stu-id="2cce9-118">**ServiceName** (auto-populated—the orchestration name)</span></span>  
  
    -   <span data-ttu-id="2cce9-119">**ServiceInstanceID**(rellena automáticamente: el identificador de instancia de orquestación como un GUID)</span><span class="sxs-lookup"><span data-stu-id="2cce9-119">**ServiceInstanceID**(auto-populated—the orchestration instance ID as a GUID)</span></span>  
  
4.  <span data-ttu-id="2cce9-120">Código en el controlador de excepción establece otras propiedades del mensaje de error según sea necesario, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2cce9-120">Code in the exception handler sets other properties of the fault message as required, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  <span data-ttu-id="2cce9-121">El mecanismo de excepciones de ESB serializa automáticamente actual **excepción** objeto en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="2cce9-121">The ESB Exception mechanism automatically serializes the current **Exception** object into the fault message.</span></span>  
  
6.  <span data-ttu-id="2cce9-122">Si lo desea, el código en el controlador de excepciones puede agregar mensajes de orquestación actual con el mensaje de error ESB utilizando la **AddMessage (faultMsg, messageToAdd)** método.</span><span class="sxs-lookup"><span data-stu-id="2cce9-122">Optionally, code in the exception handler can add current orchestration messages to the ESB fault message using the **AddMessage(faultMsg, messageToAdd)** method.</span></span> <span data-ttu-id="2cce9-123">Este método serializa y envía el mensaje, incluidas todas las propiedades de contexto, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2cce9-123">This method serializes and persists the message, including all the context properties, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  <span data-ttu-id="2cce9-124">Código en el controlador de excepciones, publica el mensaje de error ESB en la base de datos de cuadro de mensaje con un puerto de enlace directo.</span><span class="sxs-lookup"><span data-stu-id="2cce9-124">Code in the exception handler publishes the ESB fault message to the Message Box database using a direct bound port.</span></span>  
  
8.  <span data-ttu-id="2cce9-125">Si la publicación se realiza correctamente, se producen los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="2cce9-125">If publishing succeeds, the following events occur:</span></span>  
  
    -   <span data-ttu-id="2cce9-126">Las suscripciones de puerto de orquestación o envío pueden procesar el mensaje de error ESB y extraer los mensajes agregados, junto con sus valores de propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="2cce9-126">Orchestration or send port subscriptions can process the ESB fault message and extract any added messages, complete with their context property values.</span></span>  
  
    -   <span data-ttu-id="2cce9-127">Un controlador de excepciones global (un puerto de envío) publica automáticamente el mensaje de error ESB en el Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="2cce9-127">A global exception handler (a send port) automatically publishes the ESB fault message to the ESB Management Portal.</span></span>