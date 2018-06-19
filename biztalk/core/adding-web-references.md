---
title: Agregar referencias Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- orchestrations, BPEL
- Web services, ports
- orchestrations, exporting
- Web services, projects
- Web services, references
- projects, Web services
ms.assetid: 7e40f215-f11a-4151-bcc6-e107bf36b6f6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cbf8cd4c21009190fc459312467656410dc663a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964770"
---
# <a name="adding-web-references"></a>Agregar referencias web
Antes de que pueda agregar un puerto Web, necesitará agregar una referencia Web a su proyecto de BizTalk. Una referencia Web es una descripción de un servicio Web que se encuentra disponible en su proyecto. Cuando se agrega una referencia Web al proyecto, el proyecto de BizTalk crea una orquestación Web tipo de puerto, tipos de mensajes Web, Reference.map (archivo de asignación), Reference.odx (archivo de orquestación), \< *WebService*\>. disco (archivo de descubrimiento) y \< *WebService*\>.wsdl (archivo de lenguaje de descripción de servicios Web) a su proyecto. Si su archivo de Lenguaje de descripción de servicios Web (WSDL) contiene tipos de esquemas de mensaje Web, el proyecto de BizTalk agregará Reference.xsd a su proyecto.  
  
 Una referencia Web incluye:  
  
-   Un Localizador uniforme de recursos (URL) para el servicio Web.  
  
-   Un archivo WSDL que ofrece información sobre el servicio, como los métodos disponibles, puertos y tipos de mensajes.  
  
-   Una asignación de referencias (Reference.map).  
  
 Al agregar una referencia Web, todos los métodos Web para ese servicio Web deben ser compatibles con BizTalk Server. No puede especificar atributos condicionales para los métodos Web específicos de un servicio Web.  
  
 Agregar una referencia Web al proyecto mediante el **Agregar referencia Web** cuadro de diálogo. Para obtener más información acerca de cómo agregar referencias Web, vea [en Visual Studio](../core/using-visual-studio.md).  
  
 Si planea exportar su orquestación usando el proceso de exportación del lenguaje de ejecución de procesos empresariales (BPEL), no puede hacer referencia a una referencia Web desde un proyecto existente de BizTalk. Cuando hace referencia a una referencia Web desde un proyecto existente de BizTalk, el proceso de exportación BPEL autogenerará un segundo archivo WSDL y perderá la información de enlace.  
  
## <a name="see-also"></a>Vea también  
 [Creación de puertos Web](../core/creating-web-ports.md)   
 [Consumo de servicios web](../core/consuming-web-services.md)