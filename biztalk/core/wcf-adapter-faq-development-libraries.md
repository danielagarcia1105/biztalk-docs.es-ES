---
title: 'P+F del adaptador WCF: Bibliotecas de desarrollo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d05b635a-d46d-4f7d-896b-8ed7a799e80f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45280a2cba918e68d0d27ab17c48dab5c2ffc7b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011693"
---
# <a name="wcf-adapter-faq-development-libraries"></a>P+F del Adaptador de WCF: Bibliotecas de desarrollo
## <a name="when-does-it-make-more-sense-to-use-the-wcf-adapters-vs-a-wcf-custom-binding-to-communicate-with-an-external-application-or-system"></a>¿Cuándo tiene sentido usar los adaptadores de WCF en lugar de un enlace personalizado de WCF para comunicarse con una aplicación o sistema externo?  
 Los adaptadores de WCF de BizTalk Server facilitan dos nuevos enfoques para integrar un sistema externo con BizTalk Server mediante WCF:  
  
- Puede escribir código de cliente y servicio WCF y usar los adaptadores de WCF de BizTalk Server para controlar la comunicación.  
  
- O también puede desarrollar un nuevo enlace de WCF personalizado usando el marco de WCF de .NET y usarlo en lugar del adaptador de WCF para controlar la comunicación.  
  
  Si usa los adaptadores de WCF con BizTalk Server, puede desarrollar código de cliente WCF y llamar a BizTalk Server como un Servicio WCF remoto, o bien puede escribir un Servicio WCF y configurar BizTalk Server para exponerlo como un Servicio WCF. La alternativa es que en realidad puede escribir un enlace de WCF personalizado completamente nuevo para controlar la comunicación.  
  
  La ventaja de escritura de cliente WCF estándar o código de servicio y usar los adaptadores de BizTalk Server estándar frente a escribir un elemento de enlace personalizado de WCF es que el enlace personalizado es mucho más difícil de desarrollar. El cliente o Servicio WCF resultante existe fuera del universo de administración de BizTalk Server (seguimiento, configuración e implementación). La ventaja de escribir un nuevo enlace personalizado propio y hospedarlo en un adaptador personalizado de WCF de BizTalk es que se puede integrar bien en estas funciones de administración de BizTalk Server. El costo asociado con el desarrollo de un enlace con respecto a la compatibilidad de la infraestructura es considerablemente más costoso que el del desarrollo de un servicio.  
  
  Es importante comprender que ambos enfoques proporcionan la oportunidad de integración con la base de datos de cuadro de mensajes interna de BizTalk de manera transaccional y pueden ofrecer un rendimiento similar. Se trata más bien de una decisión sobre la complejidad de la solución.  
  
  Cuando use WCF, en primer lugar debería intentar escribir un servicio y un cliente personalizado, y usar los adaptadores de WCF de BizTalk para conectarlos. Las bibliotecas de .NET Framework y WCF se centran específicamente en facilitar esta tarea. Para crear el Servicio WCF, simplemente desarrolle la interfaz personalizada, establezca los atributos adecuados e implemente el código que se encuentra detrás del contrato. WCF se encarga de todo, desde los metadatos hasta la serialización de objetos. Después de escribir el Servicio WCF, puede configurar un adaptador de WCF mediante un puerto de envío para comunicarse con el servicio en unos cuantos pasos simples. Incluso puede configurar transacciones para que el nuevo servicio pueda participar en un intercambio transaccional de mensajes con la base de datos de cuadro de mensajes de BizTalk.  
  
  En el lado de recepción, puede configurar BizTalk Server para que una ubicación de recepción parezca como un Servicio WCF en la red. Esto le permite escribir código de cliente WCF regular y puede incluso usar transacciones cuando llame a ese servicio. La ventaja de usar un adaptador de WCF de BizTalk estándar como puente configurable directamente desde el cliente WCF hasta el código de Servicio WCF es que el desarrollo es muy simple. Un adaptador de WCF proporciona un puente transaccional, de alto rendimiento, a BizTalk Server desde el entorno de Servicios WCF de forma sencilla.  
  
  En resumen, para comunicar con un sistema externo, puede escribir un Servicio WCF para interactuar con un sistema externo y, luego, escribir código para comunicarse directamente con el Servicio WCF como solución más simple para el problema. Usa un enfoque más complejo, puede escribir un nuevo enlace personalizado e integrar con BizTalk Server mediante uno de los adaptadores personalizados de WCF de mejor manera que con el servicio WCF. Escribir un nuevo enlace personalizado es un ejercicio de desarrollo de nivel inferior y complejo. La ventaja de este enfoque es que se llega a una solución muy integrada donde la administración, la configuración y el desarrollo de BizTalk Server se usan uniformemente en toda la solución. Si la funcionalidad del adaptador se desarrolla como un cliente y Servicio WCF externos, la configuración debe estar fuera del entorno de BizTalk Server y, por lo tanto, le faltará la compatibilidad de infraestructura asociada.  
  
## <a name="what-are-the-differences-between-the-wcf-adapters-and-the-adapters-in-the-biztalk-adapter-pack"></a>¿Qué diferencias hay entre los adaptadores de WCF y los adaptadores de BizTalk Adapter Pack?  
 Los adaptadores de WCF son los siete adaptadores estándar con la versión de BizTalk Server:  
  
- WCF-Custom  
  
- WCF-CustomIsolated  
  
- WCF-NetTcp  
  
- WCF-BasicHttp  
  
- WCF-WsHttp  
  
- WCF-NetNamedPipe  
  
- WCF-NetMsmq  
  
  El [BizTalk Adapter Pack](http://www.microsoft.com/biztalk/en/us/adapter-pack.aspx) es una versión de posterior a BizTalk Server que proporciona una única solución para conectar fácil y segura a los datos de línea de negocio (LOB) desde cualquier aplicación de .NET personalizadas, empresarial basado en SQL Server solución de inteligencia, o aplicaciones de negocio de Office (OBA). Los tres adaptadores disponibles en esta versión son Siebel, SAP y Oracle DB. La licencia de Adapter Pack se incluye con las ediciones de BizTalk Server Developer, Standard y Enterprise, pero no se incluye en la edición Branch. Los clientes que ya han adquirido BizTalk Server con Software Assurance también tendrán acceso a BizTalk Adapter Pack a través de ese programa.  
  
## <a name="what-is-the-recommended-order-for-deciding-to-use-the-biztalk-server-adapter-framework-the-wcf-lob-adapter-sdk-or-the-net-framework"></a>¿Cuál es el orden recomendado a la hora de tomar la decisión de usar el marco de trabajo de adaptadores de BizTalk Server, el SDK de adaptadores LOB de WCF o .NET Framework?  
 El marco de trabajo de adaptadores de BizTalk es la opción menos recomendable porque no se basa en WCF de .NET estándar. Puesto que estratégicamente la solución probablemente debe incluir WCF, ¿cuál es la mejor manera de hacerlo? La opción más fácil es escribir un cliente y Servicio WCF, y luego usar un adaptador de WCF para unirlos. Si el programa es externo a BizTalk Server, puede escribir un enlace personalizado de WCF con .NET Framework.  
  
 La única vez que elegiría el SDK de adaptador LOB de WCF como opción es si intenta resolver un problema de integración LOB muy centrado en metadatos. El SDK de adaptador LOB de WCF es únicamente otra manera de crear un enlace de WCF y se especializa en la compatibilidad de metadatos. Un ejemplo de este requisito de metadatos es cuando el sistema con el que se comunica no tiene un tipo de documento fijo. El servidor BizTalk Server envía o recibe documentos XML y los metadatos describen el diseño de los datos en el documento para que el sistema de destino pueda usarlos.  
  
## <a name="what-are-the-differences-between-the-biztalk-adapter-framework-and-the-wcf-lob-adapter-sdk"></a>¿Qué diferencias hay entre el marco de trabajo de adaptadores de BizTalk y el SDK de adaptador de LOB de WCF?  
 El marco de trabajo de adaptadores de BizTalk se usa para crear adaptadores de WCF personalizados cuando ninguno de los siete adaptadores de WCF estándar satisface los requisitos de comunicación. El marco de trabajo de adaptadores ofrece una buena compatibilidad para que los metadatos admitan aplicaciones LOB y para compartir los métodos de configuración y administración estandarizados usados por los adaptadores de WCF estándar.  
  
 El SDK de adaptador LOB de WCF permite escribir un enlace personalizado para un sistema de destino con muchos requisitos de metadatos. El objetivo del SDK de adaptador de LOB de WCF es facilitar el desarrollo uniforme de adaptadores basados en WCF orientados a metadatos reutilizables que permiten a las aplicaciones y bases de datos empresariales integrarse entre sí. Puesto que el uso del SDK de adaptador LOB de WCF produce un enlace WCF, se puede reutilizar la misma solución desarrollada en varias aplicaciones de .NET incluidas personalizado aplicaciones. NET, BizTalk Server, Microsoft Office SharePoint® Server y Microsoft SQL Server Integration Servicios. Además, el SDK de adaptador LOB de WCF proporciona un modelo de objeto de metadatos común para exponer los metadatos del sistema de destino, para que los consumidores de adaptadores examinen, busquen y recuperen contratos de WCF del adaptador. Puede descargar el SDK desde [ http://go.microsoft.com/fwlink/?LinkID=96184 ](http://go.microsoft.com/fwlink/?LinkID=96184).  
  
 Aunque el marco de trabajo de adaptadores de BizTalk y el SDK de adaptador LOB de WCF se parecen en el sentido que facilitan el desarrollo de adaptadores personalizados, se merecen destacar algunas diferencias:  
  
- El SDK de adaptador de LOB de WCF es una versión más reciente y se basa en las clases de .NET Framework 3.0. Como el marco de trabajo de adaptadores de BizTalk anterior, proporciona una eficaz funcionalidad en cuanto al procesamiento de metadatos y la administración de conexiones. Sin embargo, el adaptador resultante no está unido a la arquitectura de BizTalk Server.  
  
- Un adaptador escrito con el SDK de adaptador LOB de WCF se expone como un enlace personalizado y está disponible para que cualquier aplicación cliente WCF lo llame. También se puede extender como un canal de WCF. Únicamente un servidor BizTalk Server puede llamar a un adaptador escrito con el marco de trabajo de adaptadores de BizTalk.  
  
  No hay compatibilidad de la herramienta de desarrollo explícita para el marco de trabajo de adaptadores de BizTalk. Para el SDK de adaptador LOB de WCF, el Asistente para generación de código de adaptador realiza una serie de pasos que permite reunir información que el adaptador personalizado deberá usar y, luego, genera archivos para usarlos en el proyecto de adaptador personalizado.