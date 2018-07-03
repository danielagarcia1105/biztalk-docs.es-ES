---
title: 'Módulo 7: Probar una instancia de archivo plano válida | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, flat file instance
- tutorial, testing flat file instance
- flat files, testing
ms.assetid: ba8a5d81-41b0-4da7-8c2e-02cf29953af7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2344e537fe2b66720e0df9296e22145d1c23bfa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972253"
---
# <a name="module-7-testing-a-valid-flat-file-instance"></a><span data-ttu-id="ba36a-102">Módulo 7: Probar una instancia de archivo plano válida</span><span class="sxs-lookup"><span data-stu-id="ba36a-102">Module 7: Testing a Valid Flat File Instance</span></span>
<span data-ttu-id="ba36a-103">En este módulo, envíe un ejemplo válido MT103 que creó en los laboratorios anteriores de puertos de recepción de archivo sin formato en el archivo.</span><span class="sxs-lookup"><span data-stu-id="ba36a-103">In this module, you submit a valid sample MT103 flat file to the file receive ports created in the previous labs.</span></span> <span data-ttu-id="ba36a-104">Esta tarea comprueba las canalizaciones de recepción que creó en laboratorios anteriores.</span><span class="sxs-lookup"><span data-stu-id="ba36a-104">This task tests the receive pipelines you created in previous labs.</span></span> <span data-ttu-id="ba36a-105">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] escribe la salida en formato XML en la carpeta de salida en el puerto de envío que ha seleccionado en la lección anterior, [lección 2: agregar un puerto de envío XML](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="ba36a-105">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output in XML format to the output folder in the send port you selected in the previous lesson, [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>  
  
 <span data-ttu-id="ba36a-106">Iniciar el archivo copiando un archivo con formato sin formato de SWIFT a la carpeta de entrada del adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="ba36a-106">You initiate the file receive adapter by copying a SWIFT flat-formatted file to the inbound folder.</span></span> <span data-ttu-id="ba36a-107">Esta acción da como resultado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] enrutamiento de un archivo XML de SWIFT válido a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="ba36a-107">This action results in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] routing a valid SWIFT XML file to the outbound folder.</span></span>  
  
 <span data-ttu-id="ba36a-108">En esta tarea, también enviar un mensaje MT103 que no es válido.</span><span class="sxs-lookup"><span data-stu-id="ba36a-108">In this task, you also submit an MT103 message that is not valid.</span></span> <span data-ttu-id="ba36a-109">Utilice el evento para resolver el error.</span><span class="sxs-lookup"><span data-stu-id="ba36a-109">You use the Event to resolve the error.</span></span>  
  
 <span data-ttu-id="ba36a-110">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="ba36a-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="ba36a-111">Lección 1: Envío de un archivo plano de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba36a-111">Lesson 1: Submitting a Sample Flat File</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)  
  
-   [<span data-ttu-id="ba36a-112">Lección 2: Envío de un mensaje MT103 que no es válido</span><span class="sxs-lookup"><span data-stu-id="ba36a-112">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-submitting-an-mt103-message-that-is-not-valid.md)  
  
-   [<span data-ttu-id="ba36a-113">Lección 3: Probar una instancia XML</span><span class="sxs-lookup"><span data-stu-id="ba36a-113">Lesson 3: Testing an XML Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)