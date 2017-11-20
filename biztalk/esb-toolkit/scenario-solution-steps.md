---
title: "Pasos de solución de escenario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77751c15-9b67-4587-8bc8-2be65f13d339
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dff3b2feda86ad0b8edbbded26a290c7276a63af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-solution-steps"></a><span data-ttu-id="ee152-102">Pasos de solución de escenario</span><span class="sxs-lookup"><span data-stu-id="ee152-102">Scenario Solution Steps</span></span>
<span data-ttu-id="ee152-103">El marco de trabajo de administración de excepciones de ESB proporciona una solución sencilla para controlar una excepción cuando un mensaje de factura contiene datos no válidos que se produzca un error durante el procesamiento, como se describe anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="ee152-103">The ESB Exception Management Framework provides a simple solution for handling an exception when an invoice message contains invalid data that causes an error during processing, as described earlier in this topic.</span></span> <span data-ttu-id="ee152-104">Éste es un enfoque que puede seguir:</span><span class="sxs-lookup"><span data-stu-id="ee152-104">The following is one approach you could take:</span></span>  
  
1.  <span data-ttu-id="ee152-105">Asignar la responsabilidad de la aplicación de informes financieros recientemente implementada basada en Microsoft BizTalk a un desarrollador en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ee152-105">Assign responsibility for the recently deployed Financial Reporting application based on Microsoft BizTalk to a developer on your team.</span></span>  
  
2.  <span data-ttu-id="ee152-106">Llega un mensaje de error ESB nuevo en el Portal de administración de ESB; el mensaje indica un problema de integridad de datos en una orquestación en la aplicación de BizTalk de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="ee152-106">A new ESB fault message arrives in the ESB Management Portal; the message indicates a data integrity issue in an orchestration in the Financial Reporting BizTalk application.</span></span>  
  
3.  <span data-ttu-id="ee152-107">El administrador u operador notifica al desarrollador de la nueva excepción o el desarrollador registra para recibir notificaciones automáticas cuando se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="ee152-107">The administrator or operator notifies the developer of the new exception, or the developer registers for automatic notification when an exception occurs.</span></span> <span data-ttu-id="ee152-108">Esta notificación puede producirse por uno de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="ee152-108">This notification may occur for one of the following reasons:</span></span>  
  
    -   <span data-ttu-id="ee152-109">Puede producirse porque la excepción supera un umbral predefinido en basado en eventos actividad supervisión económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="ee152-109">It may occur because the exception exceeded a threshold predefined in event-based Business Activity Monitoring (BAM).</span></span>  
  
    -   <span data-ttu-id="ee152-110">Puede producirse porque existe una suscripción de BizTalk para la aplicación específica, el servicio, el ámbito y el código de error que reenvía la excepción para el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="ee152-110">It may occur because a BizTalk subscription exists for the specific application, service, scope, and fault code that forwards the exception to the developer.</span></span>  
  
4.  <span data-ttu-id="ee152-111">El desarrollador examina el mensaje de error, los mensajes de orquestaciones individuales y sus valores de propiedad de contexto persistente.</span><span class="sxs-lookup"><span data-stu-id="ee152-111">The developer examines the fault message, the individual orchestration messages, and their persisted context property values.</span></span> <span data-ttu-id="ee152-112">Los programadores pueden ver esta información a través del Portal de administración de ESB o mediante Microsoft Outlook a través de una suscripción de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ee152-112">Developers can view this information through the ESB Management Portal or by using Microsoft Outlook through a BizTalk subscription.</span></span>  
  
5.  <span data-ttu-id="ee152-113">El programador determina que se trata de un error común.</span><span class="sxs-lookup"><span data-stu-id="ee152-113">The developer determines that this is a common error.</span></span> <span data-ttu-id="ee152-114">Requiere intervención manual y la corrección por el equipo de finanzas, seguido de reenvío para el sistema.</span><span class="sxs-lookup"><span data-stu-id="ee152-114">It will require manual intervention and correction by the Finance team, followed by resubmission to the system.</span></span>  
  
6.  <span data-ttu-id="ee152-115">El programador crea e implementa un proyecto de orquestación de BizTalk independiente que se suscribe a un tipo específico de aplicación y la excepción.</span><span class="sxs-lookup"><span data-stu-id="ee152-115">The developer creates and deploys an independent BizTalk orchestration project that subscribes to the specific application and exception type.</span></span>  
  
7.  <span data-ttu-id="ee152-116">El proyecto de orquestación recupera el mensaje no válido desde el mensaje de error ESB, envía el mensaje al equipo de finanzas para su corrección, correlaciona el mensaje a la orquestación corregido y lo reenvía.</span><span class="sxs-lookup"><span data-stu-id="ee152-116">The orchestration project retrieves the invalid message from the ESB fault message, sends the message to the Finance team for correction, correlates the corrected message back to the orchestration, and resubmits it.</span></span>  
  
8.  <span data-ttu-id="ee152-117">Una semana más adelante, el desarrollador navega al Portal de administración de ESB para descubrir que las tendencias de la excepción de aplicación para mensajes no válidos han disminuido considerablemente desde que se implementó esta solución.</span><span class="sxs-lookup"><span data-stu-id="ee152-117">A week later, the developer navigates to the ESB Management Portal to discover that application exception trends for invalid messages have decreased dramatically since this solution was deployed.</span></span>