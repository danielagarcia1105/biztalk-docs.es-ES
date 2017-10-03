---
title: "Aspectos destacados de la implementación del servicio en la solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, performance
- performance, service solutions
- service solution tutorial, implementing
ms.assetid: 3dbd8dfd-45b7-4290-ba07-b0c5e6264629
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c593c24c72e5666525001e6a52e2b0bf6eac2de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a>Aspectos destacados de la implementación del servicio en la solución orientada a servicios
Una solución resuelve un problema concreto en un contexto específico. La solución orientada a servicios no es una excepción y es específica para Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el escenario. Para obtener más información acerca del escenario de Woodgrove Bank, vea [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).  
  
 Durante el desarrollo del escenario, varias áreas resultaron ser cuellos de botella al reducir los tiempos de respuesta a un nivel aceptable. El envío de mensajes a los sistemas de servidor mediante adaptadores provoca una notable latencia en la obtención de respuestas. En general, los adaptadores de por sí ofrecen una latencia muy baja. Sin embargo, la arquitectura distribuida de BizTalk requiere que los adaptadores se comuniquen con las instancias de host de las orquestaciones mediante el cuadro de mensajes. Esto produce acciones de ida y vuelta a la base de datos y afecta a los tiempos de latencia. Por este motivo, la versión en línea de la solución (la versión más rápida) hace que la funcionalidad del adaptador de la propia orquestación llame directamente a los sistemas de servidor. Es decir, con tres sistemas de servidor diferentes, potencialmente hay tres mecanismos distintos para comunicarse con los sistemas de servidor.  
  
 Otra área que mostraba problemas de rendimiento era la recuperación de datos de configuración desde el inicio de sesión único (SSO) empresarial. Para conservar la comodidad y la universalidad de SSO a la vez que se acelera el tiempo de recuperación, la solución emplea una caché local para los valores de configuración. El uso de SSO también permite realizar una administración más fácil de los datos de configuración. Con la agregación de más instancias de host para satisfacer los requisitos de latencia y de rendimiento no es necesario cambiar valores en el servidor que ejecuta la instancia de host.  
  
 Otro elemento inusual de la solución es la llamada a las canalizaciones directamente desde el código. Esto permite volver a utilizar los componentes de canalización personalizados.  
  
 Por último, hay varios valores de BizTalk Server que se pueden modificar para obtener el último resquicio de velocidad de la solución.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [La inclusión de Back-end invocación](../core/inlining-back-end-invocation.md)  
  
-   [Usar SSO de forma eficaz en el servicio de solución orientada a servicios](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [Uso de canalizaciones desde el servicio solución orientada a servicios](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [Ajustar la solución orientada a servicios](../core/tuning-the-service-oriented-solution.md)  
  
-   [Separar tipo de transporte y procesamiento](../core/decoupling-transport-type-and-processing.md)