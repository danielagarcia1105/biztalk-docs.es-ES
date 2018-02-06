---
title: "Introducción a BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06a4a31a-eefe-4b1b-89ca-2cba2b6fa587
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4de6778bef644dc7bbfa25b46c28b36e1741ba6f
ms.sourcegitcommit: d0a1816a8dd8412906245d40c6479b08d7b3b20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="introducing-biztalk-server"></a>Introducción a BizTalk Server
Unir los sistemas se espera y se ha convertido en la norma. Dado que las organizaciones tienden a un mundo orientado a los servicios, el verdadero objetivo, es decir, la creación de procesos empresariales efectivos que aúnen sistemas independientes dentro de un todo coherente, está al alcance de todos.  
  
 Microsoft BizTalk Server permite conectar software variado para, a continuación, crear gráficamente y modificar la lógica del proceso que emplea dicho software. Además, BizTalk Server hace posible que los trabajadores de la información supervisen los procesos que están ejecutándose, interactúen con los socios comerciales y lleven a cabo otras tareas de tipo empresarial.  
  
 Las nuevas características de BizTalk Server son:  
  
-   Soporte mejorado para la implementación, la supervisión y la administración de aplicaciones.  
  
-   Instalación significativamente más sencilla.  
  
-   Capacidades mejoradas para la Supervisión de la actividad económica (BAM).  
  
BizTalk Server también usa las versiones más recientes de otras tecnologías de Microsoft. Se basa en .NET Framework, y las herramientas de desarrollo están hospedadas en Microsoft Visual Studio. Para el almacenamiento, BizTalk Server utiliza SQL Server. BizTalk Server puede ejecutar en servidores de Windows de 64 bits, sacar partido de la máxima cantidad de memoria y otras ventajas que ofrece el hardware.  
  
## <a name="what-is-biztalk-server"></a>¿Qué es BizTalk Server?  
 La combinación de distintos sistemas en procesos empresariales efectivos supone todo un desafío. En consecuencia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye una amplia variedad de tecnologías. La siguiente ilustración muestra los componentes más destacados del producto.  
  
 ![Información general de componentes de BizTalk Server](../core/media/d167608e-7c51-4d52-b8fa-9d4149242934.gif "d167608e-7c51-4d52-b8fa-9d4149242934")  
  
 Tal y como se indica en la ilustración, el motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es el componente principal del producto. Este motor cuenta con dos piezas principales:  
  
-   Un componente de mensajería que proporciona la capacidad de establecer una comunicación con otros tipos de software. Dado que depende en adaptadores para distintos tipos de comunicación, el motor admite una amplia gama de protocolos y formatos de datos, incluidos los servicios web, entre otros.  
  
-   Un soporte para la creación y ejecución de procesos definidos gráficamente, las orquestaciones. Las orquestaciones, integradas sobre los componentes de mensajería del motor, implementan la lógica que dirige un proceso empresarial completo o parte de éste.  
  
 Junto con el motor pueden usarse, además, otros componentes de BizTalk, entre los que se incluyen los siguientes:  
  
-   Un motor de reglas de negocios que evalúa conjuntos complejos de reglas.  
  
-   Un concentrador de grupo que permite a los programadores y administradores supervisar y administrar el motor y las orquestaciones que éste ejecuta.  
  
-   Una función de inicio de sesión único (SSO) empresarial que proporciona la capacidad de asignar datos de autenticación entre Windows y otros sistemas ajenos.  
  
 Sobre esta base, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye supervisión de la actividad económica, que los trabajadores de la información usan para controlar los procesos empresariales que se llevan a cabo. El tipo de información que se muestre dependerá de las preferencias de los usuarios empresariales y se expresará en términos empresariales, en lugar de técnicos.  
  
## <a name="connecting-diverse-systems"></a>Conectar sistemas diferentes  
 La gran mayoría de los procesos empresariales modernos dependen de las aplicaciones de software en mayor o menor medida. Así, si bien algunos de estos procesos dependen una sola aplicación, muchos otros están basados en distintos sistemas de software. En numerosas ocasiones, estas aplicaciones de software son diferentes respecto a la fecha de creación, la plataforma en la que se generaron y la tecnología que emplean. La automatización de esos procesos empresariales hace necesaria la conexión de sistemas distintos.  
  
 Afrontar este desafío adopta nombres diversos: automatización de procesos empresariales (BPA), administración de procesos empresariales (BPM) y otros. Independientemente del nombre, la mayor importancia de la integración de aplicaciones la adquieren dos escenarios. El primero es la conexión de las aplicaciones en una única organización, denominada habitualmente Integración de aplicaciones de negocios (EAI). El segundo, denominado Integración negocio a negocio (B2B), conecta las aplicaciones en distintas organizaciones.  
  
 La siguiente ilustración muestra un sencillo ejemplo del motor principal de BizTalk Server aplicado a un problema de EAI. En este escenario, una aplicación de inventario, que puede estar ejecutándose en un gran sistema IBM, advierte que quedan pocos repuestos de un elemento, por lo que emite una solicitud para pedir más material. Esta solicitud se envía a la orquestación de BizTalk Server (paso 1) que, a continuación, emite una solicitud de pedido a esta aplicación ERP de la organización (paso 2). La aplicación ERP, que puede estar ejecutándose en un sistema Unix, devuelve el pedido solicitado (paso 3), y la orquestación de BizTalk Server informa a una aplicación de procesamiento, integrada quizás en Windows mediante .NET Framework, de que debería solicitarse dicho elemento (paso 4).  
  
 ![EAI implementado en el motor de BizTalk.](../core/media/7d8558da-03cf-494b-8334-efe0ea15a6a7.gif "7d8558da-03cf-494b-8334-efe0ea15a6a7")  
  
 En este ejemplo, cada aplicación se comunica mediante un protocolo diferente. Por consiguiente, el componente de mensajería del motor de BizTalk Server debe ser capaz de comunicarse con cada aplicación en su estilo de comunicación nativo. Además, tenga en cuenta que ninguna aplicación es consciente del proceso empresarial completo. La inteligencia necesaria para coordinar todas las partes implicadas del software se implementa en la orquestación de BizTalk Server.  
  
 La conexión de aplicaciones dentro de una organización resulta de importancia, pero la conexión de aplicaciones que abarquen varias empresas puede ser crucial. La siguiente ilustración muestra un ejemplo sencillo de este tipo de integración negocio a negocio. En este caso, la organización que realiza el pedido, situada en la parte superior de la ilustración, ejecuta una orquestación de BizTalk Server que interactúa con dos organizaciones proveedoras. El Proveedor A también utiliza BizTalk Server, con lo que proporciona acceso indirecto a su aplicación de suministro. El proveedor B usa una plataforma de integración de otro fabricante y se conecta a la orquestación de BizTalk Server de la organización que realiza el pedido mediante, por ejemplo, los servicios web.  
  
 ![Diagrama de integración negocio a negocio](../core/media/b1d8787d-e842-468e-96c5-b68875d9abc3.gif "b1d8787d-e842-468e-96c5-b68875d9abc3")  
  
## <a name="see-also"></a>Vea también  
 [Descripción de BizTalk Server](../core/understanding-biztalk-server.md)
