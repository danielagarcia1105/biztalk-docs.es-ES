---
title: Tutoriales para obtener información sobre el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99002b01-da8a-483e-ada3-1ffbe9cd7357
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e98ba2cd875df0def595f55786990d64b9234288
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011061"
---
# <a name="tutorials-to-learn-the-wcf-lob-adapter-sdk"></a>Tutoriales para obtener información sobre el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tutoriales contienen información acerca de cómo puede usar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] desarrollar repleta de línea de adaptadores empresariales para facilitar la integración de aplicaciones empresariales dentro de su empresa. Mediante el uso de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], las operaciones y los datos que expone pueden utilizarse en cualquier aplicación que puede consumir un enlace WCF, incluidos [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 Los tutoriales contienen ejemplos sencillos creados en torno a un conjunto de operaciones predefinidas. No es necesario una línea real del sistema empresarial disponible para completar estos tutoriales. Sin embargo, los detalles proporcionados en los tutoriales pueden aplicarse a sus necesidades de desarrollo de adaptador, metadatos de descripción a la escritura de controladores de salida y mucho más.  

> [!TIP]
> Se incluye con los archivos de instalación de BizTalk en el adaptador de Echo completado `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` o `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.
  
 Use los siguientes tutoriales para aprender a usar las partes clave de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
- [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md). Proporciona instrucciones paso a paso para crear un adaptador que expone las operaciones de cadena de un conjunto de métodos predefinidos que actúan como la línea del sistema de negocio. El adaptador proporciona una implementación para muchos de los controladores comunes en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] como búsqueda, exploración, las operaciones de entrada y salidas. La finalización correcta de este tutorial, tendrá un adaptador funcional.  
  
- [Tutorial 2: Usar el adaptador de Echo desde .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md). Proporciona instrucciones paso a paso para consumir el adaptador de Echo desarrolladas en [Tutorial 1: desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) desde un proyecto. NET. Agregará una referencia de servicio de adaptador a un nuevo proyecto y proporcionar código para probar las operaciones entrantes y salientes del adaptador de Echo.  
  
- [Tutorial 3: Hospedar el adaptador de Echo en IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md). Proporciona instrucciones paso a paso para hospedar el adaptador de Echo desarrolladas en [Tutorial 1: desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) procesar en Internet Information Services (IIS). También utilizará svcutil.exe (utilidad de metadatos de ServiceModel) para crear una aplicación cliente sencilla para consumir la operación EchoString del adaptador hospedado.  
  
  Estos tutoriales ofrecen un enfoque estructurado para conocer algunas de las características clave de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Se puede completar sin el conocimiento de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] o [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. Sin embargo, obtendrá más información si comprenda los conceptos de diseño de adaptador y comprender cómo se facilita el diseño de adaptador en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Para obtener más información, vea:  
  
- [Tareas comunes de desarrollador para WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/common-developer-tasks-for-the-wcf-lob-adapter-sdk.md)  
  
- [Principales componentes del SDK del adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/key-components-of-the-wcf-lob-adapter-sdk.md)  
  
  Antes de comenzar estos tutoriales, debe revisar los requisitos en [antes de comenzar los tutoriales](../../core/before-you-begin-the-tutorial.md).  
  
 
## <a name="in-this-section"></a>En esta sección  
  
-   [Antes de comenzar los tutoriales](../../core/before-you-begin-the-tutorial.md)  
  
-   [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)  
  
-   [Tutorial 2: Usar el adaptador de Echo desde .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)  
  
-   [Tutorial 3: Hospedar el adaptador de Echo en IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)  
  
## <a name="see-also"></a>Vea también  
 [Introducción a BizTalk Server](../../core/getting-started-with-biztalk-server.md)