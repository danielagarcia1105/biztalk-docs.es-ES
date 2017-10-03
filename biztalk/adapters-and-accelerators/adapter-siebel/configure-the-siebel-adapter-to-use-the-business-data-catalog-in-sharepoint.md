---
title: "Configure el adaptador de Siebel para integrar el sistema Siebel con los datos empresariales catálogo y SharePoint | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49b575e8-5f33-4e6e-a914-95d357671ab5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d02e14b8c996acbfb07f9d422aee70cb0d94fa59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-siebel-adapter-to-integrate-the-siebel-system-with-the-business-data-catalog-and-sharepoint"></a>Configure el adaptador de Siebel para integrar el sistema Siebel con los datos empresariales catálogo y SharePoint
El [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] incluye la [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], lo cual genera un servicio WCF para los artefactos LOB específicos. Este servicio WCF se hospeda en un entorno de hospedaje, como Microsoft Internet Information Services (IIS). El Editor de definición del catálogo de datos profesionales usa la dirección URL donde se hospeda el servicio WCF para obtener el lenguaje de descripción de servicios Web (WSDL) para el servicio WCF. Con el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos disponibles para el servicio WCF. Estos métodos se pueden utilizar para establecer las entidades y la asociación entre las entidades.  
  
 El Editor de definición del catálogo de datos profesionales le ayuda a crear un archivo de definición de aplicación (un archivo XML) que puede utilizar Microsoft Office SharePoint Server. Una vez importado el archivo de definición de aplicación para Microsoft Office SharePoint Server, puede crear elementos Web para presentar la información de las aplicaciones empresariales. Para obtener más información, vea "Crear elementos Web" en [paso 3: crear una aplicación de SharePoint para recuperar datos de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) en [Tutorial 1: presentar datos desde un sistema Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).  
  
## <a name="tutorial"></a>Tutorial  
 Para demostrar cómo usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Microsoft Office SharePoint Server, el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] incluye un tutorial que proporciona instrucciones paso a paso para presentar los datos desde un sistema Siebel en un sitio de SharePoint. Vea [Tutorial 1: presentar datos desde un sistema Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilizar el adaptador de Siebel con SharePoint](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)