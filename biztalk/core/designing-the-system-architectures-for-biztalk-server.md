---
title: Diseñar las arquitecturas de sistema de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- security, deploying
ms.assetid: b7ded72a-2487-4bb7-9894-cd13235a52c7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a18656a2d4d3827cd38a3f791af2ac856df8ce36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239276"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a>Diseñar las arquitecturas del sistema de BizTalk Server
Los requisitos de la implementación de Microsoft® BizTalk® Server en cuanto a seguridad, rendimiento, disponibilidad y funcionamiento dependen en gran medida de las necesidades, los requisitos, los socios comerciales, el tamaño, etc., de la empresa. Aunque es difícil considerar una configuración cualquiera de componentes de BizTalk Server como típica y proporcionar instrucciones para ella, en esta sección se proporcionan instrucciones y recomendaciones sobre cómo configurar las distintas características de BizTalk Server en una configuración segura distribuida para el entorno de producción de una empresa de gran tamaño.  
  
 Las arquitecturas que se presentan en esta sección tienen como objetivo ofrecerle información de referencia sobre la implementación de BizTalk Server en un entorno altamente distribuido en el que los aspectos de seguridad y defensa tienen mucha importancia. Todas las aplicaciones de BizTalk Server es probable que tenga su propio conjunto único de requisitos de seguridad basados en el dominio del problema, los protocolos usados, y el entorno en particular la solución funciona en. Rendimiento, disponibilidad y las consideraciones de costo más influyen en estos requisitos. Debe utilizar estas arquitecturas y las recomendaciones que se indican en este documento como la base para crear una implementación de BizTalk Server propia que se adapte a las necesidades, las amenazas y los activos de la empresa.  
  
 Esta sección contiene información acerca de cómo puede diseñar la arquitectura del sistema de BizTalk Server con el fin de proteger las distintas características de BizTalk Server y, por consiguiente, los datos que los servidores procesan y almacenan, además de cómo integrar los servidores en un entorno distribuido que reduzca al mínimo los riesgos potenciales a los que se pueden ver sometidos los datos y servidores principales ante un ataque o desastre. Esta sección no ofrece recomendaciones para configurar entornos de desarrollo o de pruebas, ni detalles para implementar un ensamblado en un entorno de producción. Para obtener más información sobre cómo implementar ensamblados, vea [implementación de aplicación de BizTalk de descripción y administración](../core/understanding-biztalk-application-deployment-and-management.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Diseñar una arquitectura segura](../core/designing-a-secure-architecture.md)  
  
-   [Diseñar una arquitectura distribuida](../core/designing-a-distributed-architecture.md)  
  
-   [Arquitecturas de BizTalk Server de ejemplo](../core/sample-biztalk-server-architectures.md)