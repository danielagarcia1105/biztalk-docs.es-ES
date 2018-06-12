---
title: 'Lección 3: Probar una instancia XML | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, XML instances
- XML instances
ms.assetid: 19d7dd18-17dc-4355-a4f1-5c5e6750faf3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb9d5ada3054219b1387d92f4244475037c26ac
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848900"
---
# <a name="lesson-3-testing-an-xml-instance"></a><span data-ttu-id="8a7d7-102">Lección 3: Probar una instancia XML</span><span class="sxs-lookup"><span data-stu-id="8a7d7-102">Lesson 3: Testing an XML Instance</span></span>
<span data-ttu-id="8a7d7-103">En esta lección, se envía un MT103 válido que creó en las lecciones anteriores de puertos de recepción de mensaje en formato XML en el archivo.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-103">In this lesson, you submit a valid MT103 message in XML format to the file receive ports created in the previous lessons.</span></span> <span data-ttu-id="8a7d7-104">Esta acción comprueba las canalizaciones de envío que creó en módulos anteriores.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-104">This action tests the send pipelines that you created in previous modules.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="8a7d7-105">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Escribe la salida como un archivo sin formato en la carpeta de salida que seleccionó para el puerto de envío en el módulo anterior.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-105">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output as a flat file to the output folder that you selected for the send port in the previous module.</span></span>  
  
 <span data-ttu-id="8a7d7-106">Iniciar el archivo de adaptador de recepción mediante la copia de un archivo con formato XML de SWIFT a la carpeta entrante.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-106">You initiate the file receive adapter by copying a SWIFT XML-formatted file to the inbound folder.</span></span> <span data-ttu-id="8a7d7-107">Esta acción hace que el sistema copia un archivo plano SWIFT válido a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-107">This action results in the system copying a valid SWIFT flat file to the outbound folder.</span></span>  
  
### <a name="to-test-an-xml-instance"></a><span data-ttu-id="8a7d7-108">Para probar una instancia XML</span><span class="sxs-lookup"><span data-stu-id="8a7d7-108">To test an XML Instance</span></span>  
  
1.  <span data-ttu-id="8a7d7-109">En el Explorador de Windows, abra \< *unidad*\>: \Labs\Outbound.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-109">In Windows Explorer, open \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="8a7d7-110">Compruebe que esta carpeta contiene el archivo de {GUID} .xml que ha enviado a esta carpeta en [lección 1: enviar un archivo plano de ejemplo](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) de este módulo.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-110">Verify that this folder contains the {GUID}.xml file that you sent to this folder in [Lesson 1: Submitting a Sample Flat File](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) of this module.</span></span>  
  
2.  <span data-ttu-id="8a7d7-111">Copie el archivo XML y péguelo en \< *unidad*\>: \Labs\Inbound\XMLFile.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-111">Copy the XML file, and paste it into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span> <span data-ttu-id="8a7d7-112">Tenga en cuenta el tiempo que pegó este archivo.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-112">Note the time that you pasted this file.</span></span>  
  
3.  <span data-ttu-id="8a7d7-113">Mover a \< *unidad*\>: \Labs\Outbound.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-113">Move to \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="8a7d7-114">Compruebe que hay un archivo denominado .txt {GUID} en esta carpeta y que la hora en la columna de fecha de modificación de este archivo se corresponde con el tiempo que pegar el archivo en \< *unidad*\>: \Labs\Inbound\ XMLFile.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-114">Verify that there is a file called {GUID}.txt in this folder, and that the time in the Date Modified column for this file corresponds to the time that you pasted the file into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
4.  <span data-ttu-id="8a7d7-115">En el Bloc de notas, abra MT103_Sample.txt en \< *unidad*\>: \Program Acelerador de BizTalk para SWIFT\SDK\Tutorial.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-115">In Notepad, open MT103_Sample.txt in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
5.  <span data-ttu-id="8a7d7-116">En otra instancia del Bloc de notas, abra .txt {GUID} en \< *unidad*\>: \Labs\Inbound\XMLFile.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-116">In another instance of Notepad, open {GUID}.txt in \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
6.  <span data-ttu-id="8a7d7-117">Compruebe que los dos archivos en el Bloc de notas contienen el mismo contenido.</span><span class="sxs-lookup"><span data-stu-id="8a7d7-117">Verify that the two files in Notepad contain the same content.</span></span>  
  
 <span data-ttu-id="8a7d7-118">Continúe con [módulo 8: reparar un mensaje no válido](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).</span><span class="sxs-lookup"><span data-stu-id="8a7d7-118">Proceed to [Module 8: Repairing an Invalid Message](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).</span></span>