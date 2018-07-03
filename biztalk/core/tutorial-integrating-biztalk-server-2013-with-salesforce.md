---
title: 'Tutorial: Integración de BizTalk Server 2013 con Salesforce | Microsoft Docs'
description: Usar Service Bus y BIzTalk Server para integrar con Salesforce
ms.custom: ''
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aecf9bcd1ef29a1324dc1b040388f17a19a71c52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011733"
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a>Tutorial: Integración de BizTalk Server 2013 con Salesforce
Revisores: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/), [Steef Ene Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] introduce a algunos adaptadores nuevos que hacen que una gran cantidad de escenarios híbridos, que implica un entorno local y las tecnologías de Azure ahora es posibles. En este tutorial, veremos cómo integrar una entidad puramente de nube como Salesforce con un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] local usando algunos de los nuevos adaptadores y [!INCLUDE[winazure](../includes/winazure-md.md)]. Antes de comenzar, debemos tener claro el objetivo comercial que intentamos alcanzar con la integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con Salesforce.  
  
 También podríamos crear soluciones híbridas que impliquen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y Salesforce con una versión anterior de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; sin embargo, la solución sería mucho más compleja si implica la interacción con Salesforce mediante un servicio Web (SOAP). Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los nuevos adaptadores, la solución es muy sencilla.  
  
## <a name="business-scenario"></a>Escenario de negocio  
 Northwind usa el sistema de CRM en línea de Salesforce como solución para mantener un seguimiento de clientes a través de la canalización de ventas. Cada vez que se crea una oportunidad de venta en el sistema Salesforce, Northwind quiere que se notifique a sus sistemas locales, como [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], para que otros sistemas que siguen en la cadena puedan recopilar datos e iniciar otros procesos relevantes. Northwind planea implementar esta solución usando los nuevos adaptadores disponibles con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e incluyendo algunos componentes de [!INCLUDE[winazure](../includes/winazure-md.md)]. El flujo de datos de un extremo a otro para la solución tiene el siguiente aspecto:  
  
- Un representante de ventas crea una “oportunidad” en el sistema Salesforce.  
  
- Cuando el estado de la oportunidad se establece en “Closed Won”, se envía una notificación a un extremo de transmisión hospedado en [!INCLUDE[winazure](../includes/winazure-md.md)].  
  
- Usando el nuevo adaptador WCF-BasicHttpRelay, se pasa la información de notificación al sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] local.  
  
- Con la información recibida con la notificación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invoca un extremo REST en Salesforce, usando el nuevo adaptador WCF-WebHttp, para obtener más información acerca de la oportunidad.  
  
- Finalmente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la información recibida de Salesforce para crear una entrada de pedido de compra en una tabla de base de datos de SQL Server local.  
  
  Estos son los pasos que debe llevar a cabo para alcanzar el objetivo de integración que se explica en esta solución. Cada uno de estos pasos implica una serie de actividades que iremos viendo conforme avancemos en la creación de la solución.  
  
  La siguiente ilustración muestra la solución de integración de un extremo a otro:  
  
  ![Escenario de integración de BizTalk Server y Salesforce](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")  
  
## <a name="prerequisites"></a>Requisitos previos  
 El siguiente software debe estar instalado en el equipo donde configure esta solución:  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
- [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
- [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
  Debe disponer de las siguientes suscripciones a servicios:  
  
- Una suscripción a [!INCLUDE[winazure](../includes/winazure-md.md)]  
  
- Cuenta de Salesforce Developer Edition  
  
## <a name="more-resources"></a>Más recursos  
 Además de este tutorial, también puede buscar en los siguientes recursos para obtener más información sobre la integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con Salesforce usando los nuevos adaptadores introducidos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Un laboratorio virtual que muestra [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y está disponible en la integración de Salesforce [ http://go.microsoft.com/fwlink/?LinkId=290930 ](http://go.microsoft.com/fwlink/?LinkId=290930).  
  
- Un ejemplo basado en este tutorial está disponible para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=290932 ](http://go.microsoft.com/fwlink/?LinkId=290932).  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Paso 1: Crear un espacio de nombres de Service Bus](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [Paso 2: Configurar el sistema de Salesforce](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [Paso 3: Crear la solución de BizTalk Server en Visual Studio](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [Paso 4: Configurar la solución de BizTalk Server](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [Paso 5: Probar la solución](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales de BizTalk Server](../core/biztalk-server-tutorials.md)