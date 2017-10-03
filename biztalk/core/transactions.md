---
title: Las transacciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74827beade56e6e54414371c9796454d3b48609e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transactions"></a><span data-ttu-id="d8d2a-102">Transactions</span><span class="sxs-lookup"><span data-stu-id="d8d2a-102">Transactions</span></span>
<span data-ttu-id="d8d2a-103">El Motor de orquestaciones de BizTalk Server administra el estado, aplica lógica empresarial e invoca las aplicaciones de admisión de procesos y/o conjuntos de transacciones complejos.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-103">The BizTalk Server Orchestration Engine manages the state, applies business logic, and invokes the supporting applications of complex processes and/or transaction sets.</span></span>  
  
 <span data-ttu-id="d8d2a-104">Los procesos empresariales se pueden componer como elementos discretos de trabajo mediante el uso de transacciones atómicas que revierten automáticamente todos los cambios en caso de errores o de una larga ejecución, las cuales pueden contener transacciones anidadas y usar el control de excepciones personalizadas para recuperarse de casos de error.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-104">Business processes can be composed as discrete pieces of work using atomic transactions that automatically roll back all changes in case of errors or long running, which can contain nested transactions and use custom exception handling to recover from error scenarios.</span></span> <span data-ttu-id="d8d2a-105">Estas semánticas de transacciones se administran generalmente a través de la construcción Ámbito del Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-105">These transactional semantics are typically managed through the Scope construct in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="d8d2a-106">Los procesos de larga duración pueden abarcar días, semanas y períodos más prolongados.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-106">The long running processes can span days, weeks, and longer time durations.</span></span> <span data-ttu-id="d8d2a-107">Los procesos de larga duración normalmente utilizan la correlación para correlacionar mensajes que se reciben con los mensajes que se pueden enviar.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-107">The long running processes typically utilize correlation to correlate messages that are received to the messages that may be sent.</span></span> <span data-ttu-id="d8d2a-108">El motor de orquestaciones normalmente deshidrata estas instancias para ahorrar recursos del sistema y rehidrata el proceso tras recibir estos mensajes correlacionados.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-108">The orchestration engine typically dehydrates these instances to conserve system resources and re-hydrates the process upon receipt of these correlated messages.</span></span> <span data-ttu-id="d8d2a-109">El motor de orquestaciones guarda el estado de la orquestación para la base de datos de cuadro de mensajes en puntos de control conocidos para realizar la recuperación ante cualquier excepción de aplicación o del sistema.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-109">The orchestration engine persists the orchestration state to the MessageBox database at known checkpoints to recover from any application or system exceptions.</span></span>  
  
 <span data-ttu-id="d8d2a-110">El modelo de programación transaccional proporcionado por el motor de orquestaciones de BizTalk incluye la compatibilidad del control de excepciones y la recuperación de transacciones con errores, transacciones atómicas que revierten automáticamente sus acciones en caso de errores, o bien transacciones de larga ejecución que pueden contener otras transacciones, además del control de excepciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-110">The transactional programming model provided for the BizTalk Orchestration engine includes support for exception handling and recovery from failed transactions, atomic transactions that automatically roll back their actions if an error occurs, or long-running transactions that can contain other transactions as well as custom exception handling.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8d2a-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d8d2a-111">In This Section</span></span>  
  
-   [<span data-ttu-id="d8d2a-112">Transacciones atómicas</span><span class="sxs-lookup"><span data-stu-id="d8d2a-112">Atomic Transactions</span></span>](../core/atomic-transactions.md)  
  
-   [<span data-ttu-id="d8d2a-113">Escenarios de uso de transacciones atómicas</span><span class="sxs-lookup"><span data-stu-id="d8d2a-113">Scenarios Using Atomic Transactions</span></span>](../core/scenarios-using-atomic-transactions.md)  
  
-   [<span data-ttu-id="d8d2a-114">Transacciones de larga ejecución</span><span class="sxs-lookup"><span data-stu-id="d8d2a-114">Long-Running Transactions</span></span>](../core/long-running-transactions.md)  
  
-   [<span data-ttu-id="d8d2a-115">Escenarios de uso de transacciones de larga ejecución</span><span class="sxs-lookup"><span data-stu-id="d8d2a-115">Scenarios Using Long-Running Transactions</span></span>](../core/scenarios-using-long-running-transactions.md)  
  
-   [<span data-ttu-id="d8d2a-116">Persistencia en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d8d2a-116">Persistence in Orchestrations</span></span>](../core/persistence-in-orchestrations.md)