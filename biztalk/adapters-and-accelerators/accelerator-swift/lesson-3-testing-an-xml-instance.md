---
title: 'Lección 3: Probar una instancia XML | Microsoft Docs'
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
ms.openlocfilehash: 5660ab4e67545b1b98785aedeaeea6e123b6d008
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971901"
---
# <a name="lesson-3-testing-an-xml-instance"></a><span data-ttu-id="c389e-102">Lección 3: Probar una instancia XML</span><span class="sxs-lookup"><span data-stu-id="c389e-102">Lesson 3: Testing an XML Instance</span></span>
<span data-ttu-id="c389e-103">En esta lección, envíe un MT103 válido creados en las lecciones anteriores de los puertos de recepción de mensajes en formato XML en el archivo.</span><span class="sxs-lookup"><span data-stu-id="c389e-103">In this lesson, you submit a valid MT103 message in XML format to the file receive ports created in the previous lessons.</span></span> <span data-ttu-id="c389e-104">Esta acción comprueba las canalizaciones de envío que creó en los módulos anteriores.</span><span class="sxs-lookup"><span data-stu-id="c389e-104">This action tests the send pipelines that you created in previous modules.</span></span> <span data-ttu-id="c389e-105">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] escribe la salida como un archivo sin formato en la carpeta de salida que seleccionó para el puerto de envío en el módulo anterior.</span><span class="sxs-lookup"><span data-stu-id="c389e-105">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output as a flat file to the output folder that you selected for the send port in the previous module.</span></span>  
  
 <span data-ttu-id="c389e-106">Iniciar el archivo copiando un archivo con formato XML de SWIFT a la carpeta de entrada del adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="c389e-106">You initiate the file receive adapter by copying a SWIFT XML-formatted file to the inbound folder.</span></span> <span data-ttu-id="c389e-107">Esta acción da como resultado el sistema copiando un archivo plano SWIFT válido en la carpeta saliente.</span><span class="sxs-lookup"><span data-stu-id="c389e-107">This action results in the system copying a valid SWIFT flat file to the outbound folder.</span></span>  
  
### <a name="to-test-an-xml-instance"></a><span data-ttu-id="c389e-108">Para probar una instancia XML</span><span class="sxs-lookup"><span data-stu-id="c389e-108">To test an XML Instance</span></span>  
  
1. <span data-ttu-id="c389e-109">En el Explorador de Windows, abra \< *unidad*\>: \Labs\Outbound.</span><span class="sxs-lookup"><span data-stu-id="c389e-109">In Windows Explorer, open \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="c389e-110">Compruebe que esta carpeta contiene el archivo de {GUID} .xml que envía a esta carpeta en [lección 1: envío de un archivo plano de ejemplo](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) de este módulo.</span><span class="sxs-lookup"><span data-stu-id="c389e-110">Verify that this folder contains the {GUID}.xml file that you sent to this folder in [Lesson 1: Submitting a Sample Flat File](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) of this module.</span></span>  
  
2. <span data-ttu-id="c389e-111">Copie el archivo XML y péguelo en \< *unidad*\>: \Labs\Inbound\XMLFile.</span><span class="sxs-lookup"><span data-stu-id="c389e-111">Copy the XML file, and paste it into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span> <span data-ttu-id="c389e-112">Tenga en cuenta el tiempo que pegó este archivo.</span><span class="sxs-lookup"><span data-stu-id="c389e-112">Note the time that you pasted this file.</span></span>  
  
3. <span data-ttu-id="c389e-113">Mover a \< *unidad*\>: \Labs\Outbound.</span><span class="sxs-lookup"><span data-stu-id="c389e-113">Move to \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="c389e-114">Compruebe que hay un archivo denominado {GUID} .txt en esta carpeta, y que la hora en la columna de fecha de modificación de este archivo se corresponde con el tiempo que pegó en el archivo de \< *unidad*\>: \Labs\Inbound\ XMLFile.</span><span class="sxs-lookup"><span data-stu-id="c389e-114">Verify that there is a file called {GUID}.txt in this folder, and that the time in the Date Modified column for this file corresponds to the time that you pasted the file into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
4. <span data-ttu-id="c389e-115">En el Bloc de notas, abra MT103_Sample.txt en \< *unidad*\>: Acelerador de BizTalk para SWIFT\SDK\Tutorial \Program Files\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c389e-115">In Notepad, open MT103_Sample.txt in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
5. <span data-ttu-id="c389e-116">En otra instancia del Bloc de notas, abra {GUID} .txt en \< *unidad*\>: \Labs\Inbound\XMLFile.</span><span class="sxs-lookup"><span data-stu-id="c389e-116">In another instance of Notepad, open {GUID}.txt in \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
6. <span data-ttu-id="c389e-117">Compruebe que los dos archivos en el Bloc de notas contienen el mismo contenido.</span><span class="sxs-lookup"><span data-stu-id="c389e-117">Verify that the two files in Notepad contain the same content.</span></span>  
  
   <span data-ttu-id="c389e-118">Continúe con [módulo 8: reparación de un mensaje no válido](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).</span><span class="sxs-lookup"><span data-stu-id="c389e-118">Proceed to [Module 8: Repairing an Invalid Message](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).</span></span>