---
title: Mediante el marco de administración de excepciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b69c9c01-e7e4-4788-8fe2-43d32075155d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8146b3f2f9be6d076cfd7dddd651ee2c9bb4d3c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991533"
---
# <a name="using-the-exception-management-framework"></a>Mediante el marco de administración de excepciones
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] usa las excepciones para comunicar los errores (por ejemplo, un mapa no implementada o reglas que no devuelven un nombre de asignación) para las transformaciones dinámicas y el enrutamiento. Cuando se produce un error en una transformación o un proceso de enrutamiento, ESB crea un mensaje de excepción y lo envía a través de un puerto de enlace directo a la base de datos de cuadro de mensaje. Lo ESB también implementa un puerto de envío denominado todos. Excepciones que se suscribe a y recupera mensajes de excepción y los publica en el Portal de administración de ESB.  

 Además, todos los ejemplos de la orquestación utilizan la orquestación de error ESB API de enrutamiento de excepción para controlar las excepciones. Puede utilizar esta API en cualquier proyecto de orquestación que implementa. La característica de excepción enrutamiento de orquestación de error de ESB proporciona una manera estándar para capturar y notificar todas las excepciones en un entorno de BizTalk Server.  

 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene varios proyectos de ejemplo que muestran cómo usar el marco de administración de excepciones de ESB. Los siguientes dos proyectos encapsulan la orquestación de error ESB API de enrutamiento de excepción:  

- **ESB. ExceptionHandling**. Este proyecto contiene todos los métodos públicos para controlar el procesamiento de mensajes de error en las orquestaciones. Debe registrar el ensamblado de este proyecto en la caché global de ensamblados en el servidor local.  

- **ESB. ExceptionHandling.Schemas.Faults**. Este proyecto contiene el esquema de mensaje de error definido por el espacio de nombres **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** y el esquema de propiedades del sistema. Debe implementar este proyecto en el contenedor de aplicación Microsoft.Practices.ESB.  

  Todos los proyectos que usan la orquestación de error ESB API de enrutamiento de excepción deben hacer referencia a los ensamblados básicos:  

- **Microsoft.Practices.ESB.ExceptionHandling.dll**  

- **Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**  

  Las secciones siguientes proporcionan más información sobre cómo usar el marco de administración de excepciones de ESB:  

- [Los miembros de la API de excepciones de ESB](../esb-toolkit/the-esb-exception-api-members.md)  

- [Creación y publicación de mensajes de error](../esb-toolkit/creating-and-publishing-fault-messages.md)  

- [Suscripción y extracción de mensajes](../esb-toolkit/subscribing-to-and-extracting-messages.md)  

- [Pasos de solución de escenarios](../esb-toolkit/scenario-solution-steps.md)
