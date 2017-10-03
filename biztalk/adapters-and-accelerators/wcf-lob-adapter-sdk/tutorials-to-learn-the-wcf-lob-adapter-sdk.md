---
title: "Tutoriales para obtener información sobre el SDK de adaptador LOB de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99002b01-da8a-483e-ada3-1ffbe9cd7357
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3efc47a5df445e18e4a78a005c31791fe1f1fa24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorials-to-learn-the-wcf-lob-adapter-sdk"></a>Tutoriales para obtener información sobre el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tutoriales contienen información acerca de cómo se puede utilizar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para desarrollar con numerosas características de línea de adaptadores de negocio para facilitar la integración de aplicaciones empresariales dentro de su empresa. Mediante el uso de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], las operaciones y los datos que exponga pueden ser utilizados por cualquier aplicación que puede utilizar un enlace WCF, incluidos los [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 Los tutoriales contienen ejemplos sencillos generados en torno a un conjunto de operaciones predefinidas. No es necesario una línea real del sistema de negocio disponible para completar estos tutoriales. Sin embargo, detalles proporcionados en los tutoriales pueden aplicarse a las necesidades de desarrollo de adaptador, metadatos de descripción para la escritura de controladores de salida y más allá.  

> [!TIP]
> Se incluye con los archivos de instalación de BizTalk en el adaptador de eco completado `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` o `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.
  
 Consulte los siguientes tutoriales para aprender a usar los elementos clave de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
-   [Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md). Proporciona instrucciones paso a paso para crear un adaptador que expone las operaciones de cadena de un conjunto de métodos predefinidos que actúan como la línea de sistema de negocio. El adaptador proporciona una implementación para muchos de los controladores comunes en la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tales como búsqueda, exploración, las operaciones de entrada y salidas. Tras la finalización correcta de este tutorial, tendrá un adaptador funcional.  
  
-   [Tutorial 2: Utilizar el adaptador de eco de .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md). Proporciona instrucciones paso a paso para consumir el adaptador de eco desarrollado en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) desde un proyecto. NET. Agregará una referencia de servicio de adaptador a un nuevo proyecto y proporcione código para comprobar las operaciones entrantes y salientes del adaptador de eco.  
  
-   [Tutorial 3: Aloja el adaptador de eco en IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md). Proporciona instrucciones paso a paso para hospedar el adaptador de eco desarrollado en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) procesar en Internet Information Services (IIS). Svcutil.exe (utilidad de metadatos de ServiceModel) también utiliza para crear una aplicación de cliente simple para consumir la operación EchoString del adaptador hospedado.  
  
 Estos tutoriales proporcionan un enfoque estructurado para comprender algunas de las características claves de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Puede completar con ningún conocimiento de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] o [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. Sin embargo, obtendrá más información si describe los conceptos básicos del diseño de adaptador y entender cómo se facilita el diseño de adaptador en la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Para obtener más información, vea:  
  
-   [Tareas comunes de desarrollador para WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/common-developer-tasks-for-the-wcf-lob-adapter-sdk.md)  
  
-   [Componentes clave de SDK del adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/key-components-of-the-wcf-lob-adapter-sdk.md)  
  
 Antes de comenzar estos tutoriales, debe revisar los requisitos de [antes de comenzar los tutoriales](../../core/before-you-begin-the-tutorial.md).  
  
 
## <a name="in-this-section"></a>En esta sección  
  
-   [Antes de comenzar los tutoriales](../../core/before-you-begin-the-tutorial.md)  
  
-   [Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)  
  
-   [Tutorial 2: Utilizar el adaptador de eco de .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)  
  
-   [Tutorial 3: Aloja el adaptador de eco en IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)  
  
## <a name="see-also"></a>Vea también  
 [Introducción a BizTalk Server](../../core/getting-started-with-biztalk-server.md)