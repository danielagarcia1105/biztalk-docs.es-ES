---
title: Configurar el Desensamblador SWIFT o ensamblador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, disassembler
- disassembler, configuring
- configuring, assembler
ms.assetid: 56e421f2-0292-40af-b878-0cba1b034e19
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8920a8b74da14eeb8186d153444ced7c54d57724
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005069"
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a><span data-ttu-id="4f109-102">Configurar el Desensamblador SWIFT o ensamblador</span><span class="sxs-lookup"><span data-stu-id="4f109-102">Configuring the SWIFT Disassembler or Assembler</span></span>
<span data-ttu-id="4f109-103">Después de agregar el SWIFT Desensamblador o ensamblador SWIFT a una canalización personalizada, debe configurarlo para proporcionar la funcionalidad que desee para el escenario concreto (por ejemplo, la habilitación o deshabilitación de detección de tipo de mensaje dinámico, anulando entrante, validación de XML Validación de motor de reglas de negocios (BRE) y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="4f109-103">After you add the SWIFT disassembler or SWIFT assembler to a custom pipeline, you must configure it to provide the functionality you want for the particular scenario (such as enabling/disabling dynamic message type discovery, inbound debatching, XML validation, Business Rule Engine (BRE) validation, and so on).</span></span> <span data-ttu-id="4f109-104">Debe configurar el Desensamblador SWIFT y ensamblador durante el tiempo de desarrollo antes de compilar e implementar las canalizaciones personalizadas que invocación.</span><span class="sxs-lookup"><span data-stu-id="4f109-104">You must configure the SWIFT disassembler and assembler during development time before you compile and deploy the custom pipelines that invoke them.</span></span> <span data-ttu-id="4f109-105">Para configurar el ensamblador/desensamblador SWIFT, seleccione el componente en el Diseñador de canalizaciones y editar las propiedades de configuración en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="4f109-105">To configure the SWIFT disassembler/assembler, select the component in Pipeline Designer and edit the configuration properties in the Properties window.</span></span>  
  
 <span data-ttu-id="4f109-106">Hacer referencia a [propiedades de configuración de SWIFT Desensamblador](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md) para obtener información detallada y las descripciones de cada propiedad de configuración, así como otra información de uso y la configuración.</span><span class="sxs-lookup"><span data-stu-id="4f109-106">Refer to [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md) for complete details and descriptions for each configuration property, as well as other usage and configuration information.</span></span>  
  
 <span data-ttu-id="4f109-107">Hacer referencia a [propiedades de configuración de ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md) para obtener información detallada y las descripciones de la propiedad de configuración de codificación de juego de caracteres, así como otra información de uso y la configuración.</span><span class="sxs-lookup"><span data-stu-id="4f109-107">Refer to [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md) for complete details and descriptions for the Encoding Charset configuration property, as well as other usage and configuration information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f109-108">Después configura, compila e implementa las canalizaciones personalizadas, cambios en la configuración será necesario volver a compilar y volver a hacer la implementación de las canalizaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="4f109-108">After you configure, compile, and deploy the custom pipelines, changes in configuration will require re-compiling and re-deployment of the custom pipelines.</span></span>  
  
 <span data-ttu-id="4f109-109">Después configura, compila e implementa sus canalizaciones personalizadas para procesar los mensajes de SWIFT, puede establecer hasta ubicaciones de recepción que utilizan el SWIFT personalizada canalización de recepción y puertos que usan su SWIFT personalizado envían una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="4f109-109">After you configure, compile, and deploy your custom pipelines for processing SWIFT messages, you can set up receive locations that use your custom SWIFT receive pipeline, and send ports that use your custom SWIFT send pipeline.</span></span> <span data-ttu-id="4f109-110">Para obtener más información sobre cómo implementar canalizaciones y configurar puertos de recepción, ubicaciones de recepción y puertos de envío, vea [módulo 4: creación de XML de recepción y puertos de envío de archivo sin formato](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md), [módulo 5: creación de recepción de archivo sin formato y Puertos de envío XML](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)y la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4f109-110">For more information about deploying pipelines and configuring receive ports, receive locations, and send ports, see [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md), [Module 5: Creating Flat File Receive and XML Send Ports](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md), and BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="4f109-111">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="4f109-111">This section contains:</span></span>  
  
-   [<span data-ttu-id="4f109-112">Configuración del desensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="4f109-112">Configuring the SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [<span data-ttu-id="4f109-113">Configuración del ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="4f109-113">Configuring the SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f109-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f109-114">See Also</span></span>  
 [<span data-ttu-id="4f109-115">Trabajar con el desensamblador y el ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="4f109-115">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)