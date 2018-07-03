---
title: En segundo plano información acerca de escenarios de ejemplo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], background information
- DFD
- TMA, examples
ms.assetid: f9518fe7-9892-44f5-8e05-fe48bdb5161a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9424de9c530fb855b21df787f87e674e8a561f5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978453"
---
# <a name="background-information-for-sample-scenarios"></a>Información general acerca de los escenarios de ejemplo
En este tema se incluye información general acerca de los escenarios de esta sección.  
  
## <a name="background-for-all-scenarios"></a>Información general para todos los escenarios  
 Antes de la reunión del modelo de amenazas principal, recopilamos la siguiente información general. Esta información es aplicable a todos los escenarios de uso que identificamos en la arquitectura de ejemplo:  
  
-   Límites y ámbito de la arquitectura  
  
-   Límites entre los componentes de confianza y  
  
-   Modelo de configuración y administración para cada componente  
  
-   Suposiciones sobre otros componentes y aplicaciones  
  
### <a name="boundaries-and-scope-of-the-architecture"></a>Límites y ámbito de la arquitectura  
  
-   El servidor de seguridad 2 protege de la red perimetral y de otros dominios del entorno (por ejemplo, los dominios corporativos para otras aplicaciones) a los servidores y aplicaciones pertenecientes al dominio de negocio electrónico.  
  
-   El servidor de seguridad 2 enruta todo el tráfico entrante y saliente al dominio de negocio electrónico.  
  
-   Todas las cuentas y grupos de usuarios que tienen acceso al entorno de BizTalk Server deben ser grupos globales en el dominio de negocio electrónico.  
  
-   El acceso está limitado a la cuenta de servicio de la instancia de host; a las aplicaciones que descargan mensajes en el servidor de recepción SQL, de archivos o de Message Queue Server, y a los administradores de BizTalk Server, inicio de sesión único (SSO) empresarial y Windows.  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a>Límites entre los componentes de confianza y de no confianza  
  
-   El servidor de seguridad 2 enruta todo el tráfico entrante y saliente al dominio de negocio electrónico.  
  
-   Use hosts de BizTalk distintos como límite de seguridad entre aplicaciones dentro de BizTalk Server.  
  
-   Utilice hosts de confianza sólo si confía en el código de la aplicación (por ejemplo, no ejecute componentes de terceros en un host de confianza).  
  
### <a name="configuration-and-administration-model-for-each-component"></a>Modelo de configuración y administración para cada componente  
 **Modelo de configuración:**  
  
- Los componentes en tiempo de ejecución de BizTalk Server sólo se instalan en los servidores BizTalk Server.  
  
- El servidor secreto principal no tiene componentes adicionales.  
  
- El servidor SQL contiene todas bases de datos de BizTalk Server.  
  
- Los servidores de las redes perimetrales no tienen ningún componente de BizTalk Server.  
  
- El cliente de administración se utiliza para administrar todos los servidores del dominio de negocio electrónico.  
  
  **Modelo de administración:**  
  
- Desde un equipo de escritorio o portátil, el administrador se conecta al equipo en el que se encuentran las herramientas administrativas (mediante una conexión de Terminal Server o de Escritorio remoto). Una vez establecida la conexión al equipo que contiene las herramientas de administración de BizTalk, el administrador puede emplearlas para administrar todos los servidores y aplicaciones del dominio.  
  
### <a name="assumptions-about-other-components-and-applications"></a>Suposiciones sobre otros componentes y aplicaciones  
 El resto de las aplicaciones y componentes que interactúan con el entorno de BizTalk Server se encuentran en dominios distintos del dominio de negocio electrónico (por ejemplo, en una red perimetral). El tráfico entre esas aplicaciones y componentes y el entorno de BizTalk Server atraviesa el servidor de seguridad 2.  
  
 Las aplicaciones de terceros para BizTalk Server proceden de un proveedor de confianza.  
  
### <a name="data-flow-diagrams"></a>Diagramas de flujo de datos  
 El elemento final de la información global de cada escenario de uso es un diagrama de flujo de datos (DFD). El DFD ilustra el flujo de los datos a través de la arquitectura. Hay un DFD diferente para cada escenario. En este documento, los diagramas de flujo de datos contienen los elementos que aparecen en la ilustración siguiente.  
  
 **Ilustración 1: elementos de DFD**  
  
 ![Elementos de DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")  
  
## <a name="background-for-adapter-scenarios"></a>Información general para escenarios de adaptadores  
 En nuestra arquitectura de ejemplo, hemos identificado los siguientes escenarios de uso basados en algunos de los adaptadores predeterminados.  
  
- Escenario de los adaptadores de HTTP y SOAP (servicios Web)  
  
- Escenario del adaptador de BizTalk para Message Queue  
  
- Escenario del adaptador de archivo  
  
- Escenario del adaptador FTP  
  
  En cada escenario, seguimos estos siguientes para completar el análisis del modelo de amenazas:  
  
- Recopilar información general  
  
- Crear y analizar el modelo de amenazas  
  
- Analizar las amenazas  
  
- Identificar las tecnologías y técnicas de mitigación  
  
  Para cada escenario, hemos intentado desarrollar evaluaciones genéricas del nivel de amenaza que pueden representar los distintos ataques. No obstante, es posible que el entorno o la experiencia sugieran que una determinada amenaza merece una evaluación distinta. Como en todos los escenarios de seguridad, sus propios datos constituyen la base más sólida para determinar los niveles de amenaza. Es recomendable que realice su propio análisis tomando nuestros análisis y resultados como referencia.  
  
  La información en segundo plano, salvo el diagrama de flujo de datos (DFD): es el mismo para los cuatro escenarios de uso. En las secciones siguientes se muestra el DFD de cada escenario.  
  
## <a name="see-also"></a>Vea también  
 [Análisis de modelo de amenazas](../core/threat-model-analysis.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenazas](../core/sample-scenarios-for-threat-model-analysis.md)   
 [Planear la seguridad](../core/planning-for-security.md)   
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)