---
title: Descripción de la solución de administración de procesos empresariales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solutions, resources
- process management solutions, applications
- process management solution tutorial, background information
- process management solutions, about process management solutions
- applications, process management solutions
ms.assetid: fa6ad8d2-08d7-4770-9394-835f99bfd146
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4742ad9625c91c9a8f92f8359c4e0becbb166eab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004909"
---
# <a name="understanding-the-business-process-management-solution"></a>Comprender la solución de administración de procesos empresariales
La solución que se describe en esta sección explica una forma de implementar una aplicación de administración de procesos empresariales. En un administrador de procesos empresariales ideal, las partes de la solución que representa el proceso empresarial, las reglas de negocios, comunicarse con sistemas de back-end específico, enviar mensajes de respuesta, son independientes de la infraestructura que admiten el proceso.  
  
 En esta solución, un sistema de pedidos de servicios de cable de Southridge Video, el proceso empresarial está dividido en varias fases. El funcionamiento de cada una de las fases está controlado por un administrador de pedidos que no entiende de reglas de negocio ni de sistemas de servidor. El administrador de pedidos recibe los pedidos de un agente, que los emite a distintos administradores.  
  
 La solución emplea en numerosas ocasiones las características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y muestra, entre otros aspectos, el uso que se hace de los mensajes en la aplicación para coordinar todas las partes de ésta.  
  
## <a name="reader-guidance"></a>Instrucciones para el lector  
 Este documento supone que usted está familiarizado con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. También supone que comprende conceptos básicos acerca de la integración de aplicaciones de negocio y servicios Web.  
  
 Además, para leer y seguir la documentación para desarrolladores, debe estar familiarizado con cómo generar aplicaciones mediante el uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y con las siguientes tareas: crear proyectos, establecimiento de referencias y depuración y pruebas de BizTalk soluciones.  
  
## <a name="ordering-cable-service-from-southridge-video"></a>Efectuar un pedido de servicio de cable de Southridge Video  
 La solución de administración de procesos empresariales implementa un sistema de pedidos de servicios de cable para Southridge Video. Los clientes se ponen en contacto por teléfono con un centro de llamadas en el que el representante del servicio de atención al cliente recibe el pedido y lo registra en el sistema de pedidos. El diagrama siguiente muestra el flujo general de un pedido en todo el sistema:  
  
 ![Flujo trabajo solución administración de procesos empresariales](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")  
  
 Los pedidos se dirigen al agente de pedidos, quien los envía al administrador de pedidos. Éste ejecuta las fases de procesamiento del pedido en el orden adecuado. Tenga en cuenta que algunos tipos de errores se dirigen a un centro de operaciones para su corrección y reenvío, y que la solución registra el historial de cada pedido en una tabla de SQL Server.  
  
 El diagrama siguiente muestra un esquema amplio de los pasos necesarios para procesar un pedido.  
  
 ![Secuencia de solución de administración de procesos de negocio](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")  
  
 Tenga en cuenta que un pedido puede actualizarse y también cancelarse.  
  
## <a name="business-requirements"></a>Requisitos empresariales  
 La solución de administración de procesos empresariales es un ejemplo de un sistema de pedidos para Southridge Video, un proveedor de servicios de cable. Muestra una forma de implementar el patrón de los procesos empresariales en Microsoft BizTalk Server. La solución utiliza una orquestación para administrar el flujo de pedidos a través de dos orquestaciones satélite que implementan el proceso empresarial. Este estructura surge de los requisitos empresariales de la solución, entre los que se incluyen los siguientes:  
  
- Capacidad para versionar el proceso empresarial.  
  
- Procesar pedidos de larga ejecución.  
  
- Modificar o cancelar pedidos que se están procesando (completar pedidos en proceso)  
  
- Evitar pedidos suspendidos  
  
- Realizar un seguimiento de los pedidos en todo el proceso  
  
- Procesar pedidos por lotes  
  
- Aceptar pedidos de centros de datos remotos  
  
- Permitir a grupos diferentes controlar las partes del procesamiento de pedidos  
  
- Escalar la aplicación con nuevos grupos de BizTalk  
  
- Exponer el administrador de pedidos como servidor de aplicaciones mediante su establecimiento como sistema remoto  
  
  Los requisitos empresariales de Southridge Video generan una estructura de tres partes: un agente de pedido, un administrador de procesos y el propio proceso de negocio. Southridge Video posee dos grupos de TI independientes implicados en la aplicación. Un grupo de mensajería se encarga de mantener la infraestructura de mensajería corporativa y proporciona los componentes necesarios para conectar las aplicaciones a la infraestructura. Otro grupo escribe las aplicaciones en procesos empresariales concretos y lleva a cabo su mantenimiento. Por consiguiente, el agente de pedidos forma un eslabón independiente respecto al administrador de pedidos y las fases del proceso, y puede establecerse como un grupo aislado. Puesto que se trata de un componente independiente, el agente de pedidos también puede distribuir pedidos a varios administradores de procesos. Existe la posibilidad de agregar un administrador de procesos para sustentar una línea empresarial nueva, como, por ejemplo, un servicio especial.  
  
  Pedidos de Southridge Video son largos procesos en ejecución: un pedido de cable puede tardar desde un minuto en un año en completarse. Puesto que una instancia de orquestación de BizTalk debe ejecutarse hasta su finalización, es posible que transcurra un año hasta que finalice su existencia.  
  
  Southridge Video requiere una arquitectura de procesos de larga ejecución en la que los componentes de la aplicación puedan cambiar durante el procesamiento de pedidos. De esta forma, Southridge divide el procesamiento en varias fases con objeto de que un pedido pueda completarse con los componentes más novedosos. Para obtener información sobre cómo determinar los límites de la fase en un proceso empresarial, consulte [algunos principios de diseño en la solución de administración de procesos empresariales](../core/some-design-principles-in-the-business-process-management-solution.md).  
  
  Asimismo, una duración prolongada en el procesamiento de los pedidos también determina en parte la necesidad de realizar cambios en los pedidos que aún no hayan finalizado. La modificación de los pedidos es una de las razones por las que la solución incluye un amplio sistema de interrupciones. Este sistema de interrupciones facilita la realización de cambios y cancelaciones en pedidos sin completar. La solución utiliza mensajes .NET para establecer una comunicación entre las partes funcionales de la solución y controlar las interrupciones.  
  
  Dado que el sistema posee numerosas dependencias externas, puede tratar de ejecutar de nuevo algunas operaciones en caso de error. Por ejemplo, si un sistema de servidor no se encuentra disponible y se agota el tiempo de espera de una solicitud, la solución aguarda el intervalo adecuado y vuelve a emitir la solicitud. Puesto que las conexiones a sistemas externos se realizan a través de códigos personalizados, este componente de la solución hace uso de la reflexión de .NET para que los métodos de objeto traten de ejecutarse de nuevo.  
  
  La solución supone que, como ocurre en la empresa en el mundo real, los problemas del procesamiento de pedidos pueden resolverlos los miembros de un grupo de operaciones. De la misma forma, algunos de los errores que se producen en los pedidos se devuelven al representante del servicio de atención al cliente, que puede cancelar o corregir el pedido y volver a enviarlo.  
  
## <a name="business-process-management-solution-resources"></a>Recursos de la solución de administración de procesos empresariales  
 Lea los documentos siguientes si desea obtener información adicional sobre la solución de administración de procesos empresariales.  
  
### <a name="business-process-management-solution-resources"></a>Recursos de la solución de administración de procesos empresariales  
  
-   [Desarrollar una solución de administración de procesos empresariales](../core/developing-a-business-process-management-solution.md)  
  
     Los programadores y arquitectos de software pueden utilizar esta guía para documentar todas las cuestiones relativas al diseño de rendimiento, arquitectura, patrones y códigos necesarias para generar y ejecutar la aplicación de procesos empresariales.  
  
-   [Implementación de la solución de administración de procesos empresariales](../core/deploying-the-business-process-management-solution.md)  
  
     El profesional de TI con conocimientos generales de BizTalk Server puede utilizar esta guía para generar y ejecutar la aplicación Administración de procesos empresariales. En esta guía se supone que el usuario posee un conocimiento general del funcionamiento de la aplicación en un entorno distribuido.  
  
## <a name="see-also"></a>Vea también  
 [Solución de administración de procesos empresariales](../core/business-process-management-solution.md)