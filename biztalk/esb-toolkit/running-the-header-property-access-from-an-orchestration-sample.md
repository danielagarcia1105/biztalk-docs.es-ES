---
title: Ejecuta el acceso a la propiedad de encabezado de un ejemplo de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2059eb2c-50a3-4618-a6ec-faa1a9e5d368
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ddbb2ea7ef978c0e5eae07835d5a9c1320bbc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294780"
---
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a><span data-ttu-id="719a7-102">Ejecuta el acceso a la propiedad de encabezado de un ejemplo de orquestación</span><span class="sxs-lookup"><span data-stu-id="719a7-102">Running the Header Property Access from an Orchestration Sample</span></span>
<span data-ttu-id="719a7-103">Esta parte del ejemplo muestra cómo ESB promociona metadatos de encabezado JMS en Propiedades de contexto de mensaje, que pueden tener acceso código y los componentes en orquestaciones en Microsoft BizTalk.</span><span class="sxs-lookup"><span data-stu-id="719a7-103">This part of the sample demonstrates how the ESB promotes JMS header metadata into message context properties, which code and components in orchestrations within Microsoft BizTalk can access.</span></span> <span data-ttu-id="719a7-104">El ejemplo incluye una canalización de recepción que contiene una instancia del componente ESB JMS que promociona metadatos de encabezado JMS en Propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="719a7-104">The sample includes a receive pipeline that contains an instance of the ESB JMS component that promotes JMS header metadata into message context properties.</span></span>  
  
 <span data-ttu-id="719a7-105">El puerto de recepción pasa el mensaje a una orquestación JMSRouter con nombre que recupera el nombre de cola asignado por la utilidad RfhUtil (y enviado en los metadatos de encabezado) de las propiedades de contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="719a7-105">The receive port passes the message to an orchestration named JMSRouter that retrieves the queue name assigned by the RfhUtil utility (and sent in the header metadata) from the context properties of the message.</span></span> <span data-ttu-id="719a7-106">La orquestación asigna este nombre de cola a un puerto de envío dinámico y envía el mensaje a ese puerto.</span><span class="sxs-lookup"><span data-stu-id="719a7-106">The orchestration assigns this queue name to a dynamic send port and sends the message to that port.</span></span>  
  
 <span data-ttu-id="719a7-107">Una canalización de envío para el puerto contiene una instancia del componente ESB JMS que degrada las propiedades de contexto de mensaje en los metadatos de encabezado JMS.</span><span class="sxs-lookup"><span data-stu-id="719a7-107">A send pipeline for the port contains an instance of the ESB JMS component that demotes the message context properties into the JMS header metadata.</span></span>  
  
 <span data-ttu-id="719a7-108">**Para ejecutar el ejemplo de acceso a la propiedad de encabezado**</span><span class="sxs-lookup"><span data-stu-id="719a7-108">**To run the Header Property Access sample**</span></span>  
  
1.  <span data-ttu-id="719a7-109">Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="719a7-109">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="719a7-110">Ejecute la utilidad IBM RfhUtil; Seleccione el Administrador de cola denominado ESB. JMS. Sample.QueueManager en la primera lista desplegable para conectarse a este administrador de cola, como en la parte 1 de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="719a7-110">Run the IBM RfhUtil utility; select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager, as in Part 1 of this sample.</span></span>  
  
3.  <span data-ttu-id="719a7-111">En la segunda lista desplegable, seleccione la cola de salida de destino denominada ESB. JMS. EJEMPLO. SENDTOBIZTALK.</span><span class="sxs-lookup"><span data-stu-id="719a7-111">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
4.  <span data-ttu-id="719a7-112">Haga clic en el **ReadFile** situado en la utilidad RfhUtil y, a continuación, navegue hasta el archivo de mensaje de prueba denominado 000128 de prueba. JMS ubicado en la subcarpeta denominada \Source\Samples\JMS\Test\Data\Load\\.</span><span class="sxs-lookup"><span data-stu-id="719a7-112">Click the **ReadFile** button in the RfhUtil utility, and then navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="719a7-113">Este archivo contiene un lote de mensajes de prueba 128, pero la utilidad carga solo la primera de ellas.</span><span class="sxs-lookup"><span data-stu-id="719a7-113">This file contains a batch of 128 test messages, but the utility loads only the first one.</span></span>  
  
5.  <span data-ttu-id="719a7-114">Haga clic en el **RFH** ficha y, a continuación, asegúrese de que sólo el **JMS** casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="719a7-114">Click the **RFH** tab, and then make sure that only the **JMS** check box is selected.</span></span>  
  
6.  <span data-ttu-id="719a7-115">Haga clic en el **jms** ficha y, a continuación, asegúrese de que el seleccionado **responder a** cola es ESB. JMS. EJEMPLO. RESPUESTA y que el seleccionado **cola de destino** es ESB. JMS. EJEMPLO. DYNAMICQ2.</span><span class="sxs-lookup"><span data-stu-id="719a7-115">Click the **jms** tab, and then make sure that the selected **Reply To** queue is ESB.JMS.SAMPLE.REPLY and that the selected **Destination Queue** is ESB.JMS.SAMPLE.DYNAMICQ2.</span></span>  
  
7.  <span data-ttu-id="719a7-116">Haga clic en el **Main** ficha y, a continuación, haga clic en el **escribir preguntas** botón para escribir el mensaje en la cola.</span><span class="sxs-lookup"><span data-stu-id="719a7-116">Click the **Main** tab, and then click the **Write Q** button to write the message into the queue.</span></span>  
  
8.  <span data-ttu-id="719a7-117">Después de un retraso mientras se ejecuta la aplicación, aparece el mensaje de salida ESB en ESB. JMS. EJEMPLO. Cola de DYNAMICQ2.</span><span class="sxs-lookup"><span data-stu-id="719a7-117">After a delay while the application executes, the ESB output message appears in the ESB.JMS.SAMPLE.DYNAMICQ2 queue.</span></span> <span data-ttu-id="719a7-118">Abra el Explorador de la cola de WebSphere y examinar las colas para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="719a7-118">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>  
  
## <a name="how-the-sample-works"></a><span data-ttu-id="719a7-119">Cómo funciona el ejemplo</span><span class="sxs-lookup"><span data-stu-id="719a7-119">How the Sample Works</span></span>  
 <span data-ttu-id="719a7-120">Dentro de la orquestación, código puede tener acceso a los valores que se encontraban en los encabezados JMS cargando el mensaje en una **XmlDocument** instancia, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="719a7-120">Inside the orchestration, code can access the values that were in the JMS headers by loading the message into an **XmlDocument** instance, as shown in the following code.</span></span>  
  
```csharp  
if (null != InboundMsg(  
    Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData))  
{     
  jmsInfo.LoadXml(InboundMsg(  
     Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData));  
  if (null != jmsInfo)  
  {  
    if (null != jmsInfo.SelectSingleNode("//Dst"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Dst");  
      destinationQueue = xElement.InnerText.ToUpper(  
                         System.Globalization.CultureInfo.CurrentCulture);  
    }  
    if (null != jmsInfo.SelectSingleNode("//Rto"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Rto");  
      replyToQueue = xElement.InnerText.ToUpper(  
                     System.Globalization.CultureInfo.CurrentCulture);  
    }  
  }  
}  
```  
  
 <span data-ttu-id="719a7-121">Además, el código puede tener acceso a todas las propiedades de contexto MQMD del mensaje.</span><span class="sxs-lookup"><span data-stu-id="719a7-121">In addition, the code can access all of the MQMD context properties of the message.</span></span>