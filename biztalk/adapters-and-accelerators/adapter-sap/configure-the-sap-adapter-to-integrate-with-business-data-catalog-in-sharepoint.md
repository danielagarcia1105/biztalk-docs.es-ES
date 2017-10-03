---
title: "Configure el adaptador SAP para SAP se integran con los datos empresariales catálogo y SharePoint | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ec105c9-0ced-4a45-bc0d-eb72c1ef5d9d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9de78148af79cc8668d01c220799187770c7df4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sap-adapter-to-integrate-sap-with-the-business-data-catalog-and-sharepoint"></a>Configure el adaptador SAP para SAP se integran con los datos empresariales catálogo y SharePoint
El [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] incluye la [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], lo cual genera un servicio WCF para los artefactos LOB específicos. Este servicio WCF se hospeda en un entorno de hospedaje, como Microsoft Internet Information Services (IIS). El Editor de definición del catálogo de datos profesionales usa la dirección URL donde se hospeda el servicio WCF para obtener el lenguaje de descripción de servicios Web (WSDL) para el servicio WCF. Con el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos disponibles para el servicio WCF. Estos métodos se pueden utilizar para establecer las entidades y la asociación entre las entidades.  
  
 El Editor de definición del catálogo de datos profesionales le ayuda a crear un archivo de definición de aplicación (un archivo XML) que puede utilizar Microsoft Office SharePoint Server. Una vez importado el archivo de definición de aplicación para Microsoft Office SharePoint Server, puede crear elementos Web para presentar la información de las aplicaciones empresariales. Para obtener más información, vea "Crear elementos Web" en [paso 3: crear una aplicación de SharePoint para recuperar datos de SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) en [Tutorial 1: presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).  
  
## <a name="tutorial"></a>Tutorial  
 Para demostrar cómo usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Microsoft Office SharePoint Server, el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] incluye un tutorial que proporciona instrucciones paso a paso para presentar datos de un sistema SAP en un sitio de SharePoint. Vea [Tutorial 1: presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).  
  
## <a name="see-also"></a>Vea también  
[Utilizar el adaptador SAP con SharePoint](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)