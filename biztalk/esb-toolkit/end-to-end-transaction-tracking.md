---
title: Seguimiento de transacciones de extremo a extremo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebacd2e4-6b5c-4dc4-8361-b5b77042debc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffa49372c54dc526f45e04317e002604ac0914d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294116"
---
# <a name="end-to-end-transaction-tracking"></a><span data-ttu-id="aefaf-102">Seguimiento de transacciones de extremo a extremo</span><span class="sxs-lookup"><span data-stu-id="aefaf-102">End-to-End Transaction Tracking</span></span>
<span data-ttu-id="aefaf-103">Visibilidad de negocio se relaciona con la capacidad de operadores y los usuarios para supervisar el flujo de tráfico a través del entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aefaf-103">Business visibility relates to the ability of operators and users to monitor the flow of traffic through the run-time environment.</span></span> <span data-ttu-id="aefaf-104">Las empresas deben ser capaz de realizar un seguimiento de los procesos y las transacciones que fluyen a través de sus sistemas en cada paso para asegurarse de que pueden jugar su parte en que contribuyen a la generación de ingresos.</span><span class="sxs-lookup"><span data-stu-id="aefaf-104">Enterprises must be able to track the processes and transactions flowing through their systems at each step to ensure that they play their part in contributing to revenue generation.</span></span> <span data-ttu-id="aefaf-105">AmberPoint SMS simplifica la medida y el seguimiento de estos mensajes en Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="aefaf-105">AmberPoint SMS simplifies the measurement and tracking of these messages in Microsoft BizTalk Server.</span></span> <span data-ttu-id="aefaf-106">El sistema permite a los usuarios definir nuevas unidades de administración que se alinean con los flujos de procesos empresariales de extremo a extremo, en lugar de que se requiere para que se ajuste a la forma en que los desarrolladores elegido para empaquetar e implementar componentes de servicio individuales.</span><span class="sxs-lookup"><span data-stu-id="aefaf-106">The system allows users to define new units of management that align with end-to-end business process flows, instead of being required to conform to the way developers chose to package and deploy individual service components.</span></span> <span data-ttu-id="aefaf-107">La figura 1 muestra la pantalla para definir las unidades de administración.</span><span class="sxs-lookup"><span data-stu-id="aefaf-107">Figure 1 shows the screen for defining management units.</span></span>  
  
 <span data-ttu-id="aefaf-108">![Transacción de definición de BizTalk](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")</span><span class="sxs-lookup"><span data-stu-id="aefaf-108">![BizTalk Defining Transaction](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")</span></span>  
  
 <span data-ttu-id="aefaf-109">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="aefaf-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="aefaf-110">**Definir una transacción como una nueva unidad de administración**</span><span class="sxs-lookup"><span data-stu-id="aefaf-110">**Defining a transaction as a new unit of management**</span></span>  
  
 <span data-ttu-id="aefaf-111">Después de definir las transacciones, los usuarios pueden instrumentar y mensajes de seguimiento asociados a cada transacción con las mismas herramientas que proporcionan una visibilidad en un único servicio.</span><span class="sxs-lookup"><span data-stu-id="aefaf-111">After defining transactions, users can instrument and track messages associated with each transaction using the same tools that provide visibility into a single service.</span></span> <span data-ttu-id="aefaf-112">Estas herramientas pueden exponer las métricas de rendimiento, supervisar el rendimiento en los contratos de nivel de servicio y generar registros de mensajes, como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="aefaf-112">These tools can expose performance metrics, monitor performance against service level agreements, and generate message logs, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="aefaf-113">![Supervisión de BizTalk](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")</span><span class="sxs-lookup"><span data-stu-id="aefaf-113">![BizTalk Monitoring](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")</span></span>  
  
 <span data-ttu-id="aefaf-114">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="aefaf-114">**Figure 2**</span></span>  
  
 <span data-ttu-id="aefaf-115">**Supervisión del rendimiento de extremo a extremo de una canalización**</span><span class="sxs-lookup"><span data-stu-id="aefaf-115">**Monitoring the end-to-end performance of a pipeline**</span></span>  
  
 <span data-ttu-id="aefaf-116">Un requisito principal para la regulación de tiempo de ejecución correcta y la supervisión del sistema es la detección de eventos empresariales importantes, como las excepciones y errores de aplicación que se pueden interrumpir el procesamiento lógico empresarial de flujos de transacción.</span><span class="sxs-lookup"><span data-stu-id="aefaf-116">A major requirement for successful run-time governance and system monitoring is the detection of important business events, such as exceptions and application errors that may disrupt the logical processing of business transaction flows.</span></span> <span data-ttu-id="aefaf-117">AmberPoint SMS permite a los operadores y los usuarios para obtener una visión general operativa y eventos empresariales y para supervisar el impacto de estos eventos en todos los componentes que dependen del servicio que generó el problema.</span><span class="sxs-lookup"><span data-stu-id="aefaf-117">AmberPoint SMS allows operators and users to gain insight into operational and business events and to monitor the impact these events have on all components that depend on the service that generated the problem.</span></span> <span data-ttu-id="aefaf-118">Además, los operadores y los usuarios pueden resolver rápidamente todo el sistema para identificar la causa de un problema.</span><span class="sxs-lookup"><span data-stu-id="aefaf-118">In addition, operators and users can quickly troubleshoot the entire system to identify the root-cause of a problem.</span></span>