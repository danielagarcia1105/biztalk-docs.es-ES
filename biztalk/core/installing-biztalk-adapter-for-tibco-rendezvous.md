---
title: "Adaptador de TIBCO Rendezvous de instalación, esquemas y limitaciones | Documentos de Microsoft"
description: "Instalación, la generación de esquema y las limitaciones del adaptador de BizTalk para TIBCO Rendezvous en BizTalk Server"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6404e7e-f671-4c57-a222-0bbe7cbc334f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a158d4f627a553a87f0bc8fa08333a5864bb884
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="install-schemas-and-limitations-of-the-tibco-rendezvous-adapter"></a>Instalar, esquemas y limitaciones del adaptador de TIBCO Rendezvous

## <a name="install-and-setup"></a>Instalación y configuración

[Instalar y configurar los adaptadores para aplicaciones empresariales](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) incluye los pasos para instalar los adaptadores empresariales y también incluye información de la clave saber antes de instalar el adaptador y después de instalar el adaptador. 

## <a name="generate-schemas"></a>Generar esquemas
Un sistema TIBCO Rendezvous no incluye un repositorio de tipos de mensajes. Todos los análisis y construcciones de mensajes se incluyen en el tipo de aplicación Rendezvous. Debido a esta limitación, el adaptador no puede proporcionar capacidades de generación de esquemas.  
  
Debe escribir un esquema y usar **Agregar elemento existente** en Visual Studio para importarlo para su uso en orquestaciones. Los esquemas son muy importantes para las herramientas de desarrollo de BizTalk Server y para la integración en Visual Studio. Los programadores de BizTalk Server tienen la opción de proporcionar un esquema completo, minimalista o una versión intermedia.  

## <a name="limitations"></a>Limitaciones

- No se garantiza la exclusividad del nombre de campo. Si un mensaje de TIBCO Rendezvous contiene dos nombres de campo que son iguales, el XML resultante no es válido.  
  
-   No se proporciona la ordenación y clasificación de los campos.  
  
-   Según la documentación de TIBCO Rendezvous, los caracteres no imprimibles no se usan en nombres de asunto; sin embargo, sigue siendo posible usarlos. BizTalk Adapter para TIBCO Rendezvous no admite nombres de asunto que contengan esos caracteres.  
  
-   No se admite la conexión a daemons.  
  
-   No se admiten tipos de datos personalizados.  
  
-   No se admite la mensajería certificada en el lado de transmisión.  
-   
## <a name="next-step"></a>Paso siguiente

[Tutoriales: Uso del Adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)  