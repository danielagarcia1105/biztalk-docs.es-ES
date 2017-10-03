---
title: "Documentación de Microsoft Windows Communication Foundation línea de negocio SDK de adaptador | Documentos de Microsoft"
description: "Vínculos rápidos a instalar, introducción, planear y diseñar, desarrollar y el SDK del adaptador de LOB de WCF en BizTalk Server de la solución de problemas"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a2b098c-ef41-4cc0-8063-1fd043f1176f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8472fb56beab8f6d86ff33bebb9171d09d503ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="microsoft-windows-communication-foundation-line-of-business-adapter-sdk-documentation"></a>Documentación de Microsoft Windows Communication Foundation línea de negocio SDK de adaptador
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación incluye recursos para ayudarle a desarrollar, implementar y usar adaptadores creados con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  

## <a name="about-the-sdk"></a>Acerca del SDK  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una colección de un motor de tiempo de ejecución y herramientas que ayudan a los programadores del adaptador crean interfaces orientadas a servicios a los sistemas LOB existentes mediante WCF. El objetivo del SDK es facilitar el desarrollo uniforme de adaptadores reutilizables, orientados a metadatos, basadas en WCF que permiten a las aplicaciones empresariales, las bases de datos y plataformas de mensajería integrar entre sí.  
  
 Este SDK basadas en WCF expone un adaptador a un sistema LOB como un enlace de WCF. Para un consumidor de adaptador, el adaptador puede tener acceso como un servicio WCF convencional; el consumidor no tiene que aprender un nuevo modelo de programación. El mismo adaptador desarrollado puede reutilizarse en varias aplicaciones. NET, incluyendo las aplicaciones .NET personalizadas, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], SharePoint y Microsoft SQL Server Integration Services (SSIS) a través de un adaptador proporcionado por el desarrollador: ADO.NET corrección de compatibilidad. Además, el adaptador proporciona metadatos exploración, búsqueda y funcionalidad de recuperación; el consumidor de adaptador selectivamente puede generar contratos WCF que reflejen el modelado de tipo en vivo del sistema LOB.  
 
## <a name="readme"></a>Léame
![Icono de recursos de comunidad](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "Comunidad") [Léame y privacidad](../../adapters-and-accelerators/wcf-lob-adapter-sdk/readme-and-privacy-in-the-wcf-lob-adapter-sdk.md) describe los componentes incluidos en el SDK así como su se explican las opciones de privacidad. 

## <a name="install"></a>Install
![Introducción a icono](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [instalar el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/install-the-wcf-lob-adapter-sdk.md) enumera los pasos necesarios para instalar y desinstalar el SDK, quitar adaptadores personalizados y realice un instalación silenciosa. 

## <a name="get-started"></a>Introducción
![Introducción a icono](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [empezar a trabajar con el con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) incluye información relevante para los usuarios que está familiarizado con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], como leer conceptual y algunos tutoriales. 
  
## <a name="plan-and-design"></a>Planificación y diseño 
![Icono de arquitectura de adaptador](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md) se describe cuándo se debe utilizar un adaptador, un canal o un servicio . También debe conocer los patrones de mensajería compatibles, diseñar un URI, descripción de las transacciones y mucho más.

## <a name="develop-and-create"></a>Desarrollar y crear
![Icono de desarrollo del adaptador](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [desarrollar o crear el adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk.md) enumera algunos procedimientos recomendados, se proporcionan instrucciones sobre control de versiones, autenticación y mucho más.

## <a name="gac-and-deploy"></a>GAC e implementar
![Icono de ejemplos del adaptador](../../adapters-and-accelerators/adapter-sap/media/2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a.gif "2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a") después de crear el adaptador, el paso siguiente consiste en Agregar a la GAC, actualiza el archivo machine.config y crear un paquete de implementación. [Implementar el adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-adapter-using-the-wcf-lob-adapter-sdk.md) incluye esta información.

## <a name="troubleshoot"></a>Solucionar problemas
![Icono de solución de problemas del adaptador](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [creado mediante el SDK de adaptador LOB de WCF de adaptador de solución de problemas](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md) enumera los pasos necesarios para habilitar la traza, utilizarán contadores de rendimiento y generación de WSDL.

