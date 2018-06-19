---
title: 'TMA de ejemplo: Enterprise Single Sign-On | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], SSO
- architecture, examples
- SSO, examples
- SSO, TMA
- DFD, SSO
- examples, SSO
- examples, TMA
ms.assetid: c2c15b1b-54f3-4d1a-b3d8-6679abd41ccb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb57e7b22680844e3ddb18481aa76002df78b013
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22273196"
---
# <a name="sample-tma-enterprise-single-sign-on"></a>TMA de ejemplo: Enterprise Single Sign-On
En este tema se presenta el análisis de modelo de amenazas (TMA) del escenario del servicio de inicio de sesión único empresarial de la arquitectura de ejemplo.  
  
 La ilustración siguiente muestra la arquitectura de ejemplo básica, que incluye el escenario del servicio de inicio de sesión único empresarial.  
  
 **Figura 1: arquitectura de ejemplo básica que incluye el escenario de Enterprise Single Sign-On**  
  
 ![Componentes de la arquitectura de base](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")  
  
## <a name="step-1-collect-background-information-enterprise-single-sign-on-scenario"></a>Paso 1. Recopilar información básica (Enterprise Single Sign-On escenario)  
 En esta sección se proporciona el diagrama de flujo de datos (DFD) para utilizar el escenario de inicio de sesión único empresarial al asignar credenciales de Windows a las credenciales que se emplean para conectarse a una red de servidor.  
  
 El resto de información de segundo plano es el mismo para los cuatro escenarios de uso y se ha descrito anteriormente en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
### <a name="data-flow-diagram"></a>Diagrama de flujo de datos  
 La ilustración siguiente muestra el DFD del escenario del servicio de inicio de sesión único empresarial.  
  
 **Figura 2: DFD para el escenario de Enterprise Single Sign-On**  
  
 ![DFD para inicio de sesión único empresarial &#45; en](../core/media/tdi-sec-refarch-dfd-sso.gif "TDI_Sec_RefArch_DFD_SSO")  
  
 El flujo de datos es el siguiente:  
  
1.  El usuario, o la aplicación, inicia sesión con credenciales de Windows.  
  
2.  El servicio de inicio de sesión único (SSO) empresarial utiliza las credenciales de Windows para solicitar las credenciales de la red de servidor.  
  
3.  El servicio de inicio de sesión único (SSO) empresarial asigna las credenciales de Windows a las credenciales de servidor almacenadas en la base de datos de SSO.  
  
4.  El servicio de inicio de sesión único empresarial recupera las credenciales de servidor y las utiliza para conectar el usuario o la aplicación a la red de servidor.  
  
## <a name="step-2-create-and-analyze-the-threat-model-enterprise-single-sign-on-scenario"></a>Paso 2. Crear y analizar el modelo de amenazas (escenario único empresarial inicio de sesión)  
 Esta sección contiene el resultado del TMA del escenario del servicio de inicio de sesión único empresarial de la arquitectura de ejemplo.  
  
-   **Identificar puntos de entrada, límites de confianza y flujo de datos** -ver la información básica descrita en el paso 1 y en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
-   **Crear una lista de amenazas identificadas** -usamos la siguiente categorización para todas las entradas de DFD para identificar posibles amenazas para el escenario: **S**poofing identificar, **T** lteración con datos, **R**epudiation, **I**revelación de información, **d.** denegación de servicio, y **E**levación de privilegios. La siguiente tabla contiene la lista de amenazas que identificamos al usar el servicio de inicio de sesión único empresarial (SSO) para enviar y recibir mensajes del servidor BizTalk Server.  
  
 **Tabla 1: lista de amenazas identificadas**  
  
|Amenaza|Description|Asset|Impacto|  
|------------|-----------------|-----------|------------|  
|El servidor secreto principal es un punto de error único|Si un usuario malintencionado pone en peligro el servidor secreto principal, el equipo SSO no puede cifrar las credenciales (pero puede seguir descifrándolas).|Entorno de BizTalk Server y SSO|Denegación del servicio|  
|Un usuario malintencionado pude suplantar a un cliente o a un servidor|Si el cliente o el servidor ejecuta Windows sin la autenticación NTML, un usuario malintencionado podría suplantarlo.|Entorno de BizTalk Server y SSO|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Rechazo<br /><br /> Revelación de información<br /><br /> Denegación del servicio<br /><br /> Elevación de privilegios|  
|Un usuario malintencionado podría pueden manipular los datos durante su tránsito de un servidor a otro.|La comunicación entre servidores se realiza en texto sin cifrar, por lo que los usuarios malintencionados podrían leer la información mientras está en tránsito.|data|Manipulación de datos<br /><br /> Revelación de información|  
  
## <a name="step-3-review-threats-enterprise-single-sign-on-scenario"></a>Paso 3. Analizar las amenazas (escenario único empresarial inicio de sesión)  
 Esta sección contiene los resultados del análisis de riesgos que se realizó para las amenazas identificadas en el escenario del servicio de inicio de sesión único empresarial (SSO) de la arquitectura de referencia. Después de la reunión del modelo de amenazas principal, se analizamos las amenazas y usa el valor utilizado afectan a los siguientes categorías para identificar el riesgo de cada amenaza: **d.** años potenciales, **R**apacidad de reproducción, **E**provechamiento, **A**usuarios afectados y **d.** capacidad de descubrimiento.  
  
 La siguiente tabla contiene la evaluación del riesgo de las amenazas que identificamos al usar el servicio de inicio de sesión único empresarial para enviar y recibir mensajes del servidor de BizTalk Server.  
  
 **Tabla 2 clasificación de riesgo de las amenazas identificadas**  
  
|Amenaza|Impacto|Posibilidad del daño|Posibilidad de reproducir la amenaza|Posibilidad de que se aproveche|Usuarios afectados|Posibilidad de descubrir la amenaza|Exposición al riesgo|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|El servidor secreto principal es un punto de error único|Denegación del servicio|2|3|2|1|2|2|  
|Un usuario malintencionado pude suplantar a un cliente o a un servidor|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Rechazo<br /><br /> Revelación de información<br /><br /> Denegación del servicio<br /><br /> Elevación de privilegios|3|2|2|2|1|2|  
|Un usuario malintencionado podría pueden manipular los datos durante su tránsito de un servidor a otro.|Manipulación de datos<br /><br /> Revelación de información|3|1|1|2|1|1.6|  
  
## <a name="step-4-identify-mitigation-techniques-enterprise-single-sign-on-scenario"></a>Paso 4. Identificar las técnicas de mitigación (escenario único empresarial inicio de sesión)  
 Esta sección contiene algunas técnicas de mitigación para las amenazas identificadas en el escenario del servicio de inicio de sesión único empresarial de la arquitectura de ejemplo.  
  
 La siguiente tabla enumera las tecnologías y técnicas de mitigación para las amenazas identificadas al usar el servicio de inicio de sesión único empresarial para enviar y recibir mensajes del servidor BizTalk Server.  
  
 **Tabla 3 tecnologías y técnicas de mitigación**  
  
|Amenaza|Impacto|Exposición al riesgo|Tecnologías y técnicas de mitigación|  
|------------|------------|-------------------|--------------------------------------------|  
|El servidor secreto principal es un punto de error único|Denegación del servicio|2|Use una configuración de clústeres activo/pasivo para el servidor secreto principal.<br /><br /> Para obtener más información acerca de los clústeres del servidor secreto principal, consulte [alta disponibilidad para Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).|  
|Un usuario malintencionado pude suplantar a un cliente o a un servidor|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Rechazo<br /><br /> Revelación de información<br /><br /> Denegación del servicio<br /><br /> Elevación de privilegios|2|Si la red admite la autenticación de Kerberos, debería registrar todos los servidores SSO. Si usa la autenticación de Kerberos entre el servidor secreto principal y la base de datos de SSO, debe configurar nombres principales de servicio (SPN) en el servidor SQL Server donde se encuentra la base de datos de SSO.<br /><br /> Para obtener más información sobre cómo configurar nombres principales de servicio, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=61374](http://go.microsoft.com/fwlink/?LinkId=61374).|  
|Un usuario malintencionado podría pueden manipular los datos durante su tránsito de un servidor a otro.|Manipulación de datos<br /><br /> Revelación de información|1.6|Utilice el protocolo de seguridad de Internet (IPSec) o la Capa de sockets seguros (SSL) entre los servidores de SSO y la base de datos de SSO.<br /><br /> Para obtener más información acerca de SSL, vea el sitio Web de soporte técnico y Microsoft Help en [http://go.microsoft.com/fwlink/?LinkID=189708](http://go.microsoft.com/fwlink/?LinkID=189708).<br /><br /> Para obtener más información sobre cómo usar SSL entre todos los servidores SSO y la base de datos SSO, vea [cómo habilitar SSL para SSO](../core/how-to-enable-ssl-for-sso.md).|  
  
## <a name="see-also"></a>Vea también  
 [Análisis de modelo de amenazas](../core/threat-model-analysis.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)   
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)