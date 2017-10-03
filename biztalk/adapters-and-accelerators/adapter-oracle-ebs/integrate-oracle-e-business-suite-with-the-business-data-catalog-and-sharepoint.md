---
title: "Oracle E-Business Suite se integran con el catálogo de datos profesionales y SharePoint | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 311f605d-78b4-41a0-b231-1a00a879f637
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ddcdc04c211d4b458c08730de097422d0735ee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="integrate-oracle-e-business-suite-with-the-business-data-catalog-and-sharepoint"></a>Oracle E-Business Suite se integran con el catálogo de datos profesionales y SharePoint
El [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] incluye la [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], lo cual genera un servicio WCF para los artefactos LOB específicos. Este servicio WCF se hospeda en un entorno de hospedaje, como Microsoft Internet Information Services (IIS). El Editor de definición del catálogo de datos profesionales usa la dirección URL donde se hospeda el servicio WCF para obtener el lenguaje de descripción de servicios Web (WSDL) para el servicio WCF. Con el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos disponibles para el servicio WCF. Estos métodos se pueden utilizar para establecer las entidades y la asociación entre las entidades.  
  
 El Editor de definición del catálogo de datos profesionales le ayuda a crear un archivo de definición de aplicación (un archivo XML) que puede utilizar Microsoft Office SharePoint Server. Una vez importado el archivo de definición de aplicación para Microsoft Office SharePoint Server, puede crear elementos Web para presentar la información de las aplicaciones empresariales. Para obtener más información, vea "Crear elementos Web" en el paso 3: crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite en [Tutorial: presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).  
  
## <a name="tutorial"></a>Tutorial  
 Para demostrar cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con Microsoft Office SharePoint Server, el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] incluye un tutorial que proporciona instrucciones paso a paso para presentar los datos de Oracle E-Business Suite en un sitio de SharePoint. Vea [Tutorial: presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).  
  
## <a name="see-also"></a>Vea también  
[Utilizar el adaptador de Oracle E-Business Suite con SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)