---
title: Cómo agregar un Message1 error | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87ef85460f6ca6aea046ef9efff60fd198664cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246652"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="3b1bb-102">Cómo agregar un mensaje de error</span><span class="sxs-lookup"><span data-stu-id="3b1bb-102">How to Add a Fault Message</span></span>
<span data-ttu-id="3b1bb-103">La primera vez que creó el puerto en el sistema de servidor, contenía una solicitud y una respuesta.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-103">When you first created the port to the back-end system, it contained a request and a response.</span></span> <span data-ttu-id="3b1bb-104">Debe agregar un error para capturar la excepción.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-104">You must add a fault to capture the exception.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="3b1bb-105">Para agregar un mensaje de error</span><span class="sxs-lookup"><span data-stu-id="3b1bb-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="3b1bb-106">Haga clic en **operación de puerto**y, a continuación, seleccione un **nuevo mensaje de error**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-106">Right-click **Port Operation**, and then select a **New Fault Message**.</span></span>  
  
     <span data-ttu-id="3b1bb-107">A **error** aparece bajo la **solicitud y respuesta** en el puerto.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-107">A **Fault** appears under the **Request and Response** in the port.</span></span>  
  
2.  <span data-ttu-id="3b1bb-108">En el **Vista orquestación** pantalla, haga clic en **mensajes**y, a continuación, seleccione **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-108">On the **Orchestration View** screen, right-click **Messages**, and then select **New Message**.</span></span>  
  
     <span data-ttu-id="3b1bb-109">De este modo, se crea Message_3, que puede asignar específicamente al error.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-109">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
3.  <span data-ttu-id="3b1bb-110">Haga clic en **Message_3** para tener acceso a la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-110">Right-click **Message_3** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="3b1bb-111">Establecer el **tipo de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-111">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="3b1bb-112">Seleccione **esquema**y, a continuación, seleccione uno de **ensamblado de referencia**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-112">Select **Schema**, and then select from **ref assembly**.</span></span>  
  
         <span data-ttu-id="3b1bb-113">Se abrirá una **Seleccionar tipo de artefacto** ventana.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-113">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="3b1bb-114">Desplácese hacia abajo y seleccione el error completo.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-114">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="3b1bb-115">El nombre es **BTS. SOAP_Envelope_1__1.Fault**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-115">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span> <span data-ttu-id="3b1bb-116">Haga clic en **Aceptar** para aceptar la selección y cerrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-116">Click **OK** to accept the selection and close the window.</span></span>  
  
4.  <span data-ttu-id="3b1bb-117">Haga clic en el **error** para tener acceso a la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-117">Right-click the **Fault** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="3b1bb-118">Establecer el **tipo de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-118">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="3b1bb-119">Seleccione **esquema** y, a continuación, seleccione uno de **ref** ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-119">Select **Schema** and then select from **ref** assembly.</span></span>  
  
         <span data-ttu-id="3b1bb-120">Se abrirá una **Seleccionar tipo de artefacto** ventana.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-120">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="3b1bb-121">Desplácese hacia abajo y seleccione el error completo.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-121">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="3b1bb-122">El nombre es **BTS. SOAP_Envelope_1__1.Fault**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-122">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span>  
  
    4.  <span data-ttu-id="3b1bb-123">Haga clic en **Aceptar** para aceptar la selección y cerrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-123">Click **OK** to accept the selection and close the window.</span></span>  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  <span data-ttu-id="3b1bb-124">Una vez asignado el nombre al error, definirá este nombre en el tipo de objeto de excepción CatchException.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-124">After the fault is named, you will set this name to the CatchException's exception object type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b1bb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b1bb-125">See Also</span></span>  
 [<span data-ttu-id="3b1bb-126">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3b1bb-126">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)