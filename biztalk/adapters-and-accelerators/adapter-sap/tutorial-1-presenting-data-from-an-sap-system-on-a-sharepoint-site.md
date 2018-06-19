---
title: 'Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdc3ea5e41600aebcef1fda933735c418dec78c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217428"
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a>Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint
Este tutorial proporciona instrucciones detalladas sobre cómo utilizar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Microsoft Office SharePoint Server para presentar datos de negocio de un sistema SAP en un portal de SharePoint. Para demostrar cómo usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Office SharePoint Server, tenga en cuenta las dos entidades más comunes en las empresas: clientes y pedidos de venta. En este ejemplo, se crea una aplicación de Office SharePoint Server, que utiliza el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para hacer lo siguiente:  
  
-   Recuperar una lista de clientes desde el sistema SAP basándose en una cadena de búsqueda.  
  
-   Seleccione a un cliente en la lista y detalles presentes para el cliente.  
  
-   Recuperar los pedidos de venta para el cliente seleccionado.  
  
 Para extraer datos de los clientes de un sistema SAP, el ejemplo utiliza la RFC SD_RFC_CUSTOMER_GET. Para extraer información sobre los pedidos de ventas para un cliente específico, usa la RFC BAPI_SALESORDER_GETLIST.  
  
> [!NOTE]
>  Algunas versiones del sistema SAP exponen una solicitud de cambio de RFC_CUSTOMER_GET en lugar de SD_RFC_CUSTOMER_GET.  
  
> [!NOTE]
>  Antes de continuar con el tutorial, asegúrese de que ha instalado todos los requisitos previos para usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Office SharePoint Server. Para obtener más información sobre los requisitos previos, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación, por lo general se instala en C:/programa archivos/Microsoft  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] /documentos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Publicar los artefactos SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [Paso 2: Crear un archivo de definición de aplicación para los artefactos SAP](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [Paso 3: Crear una aplicación de SharePoint para recuperar datos de SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [Paso 4: Probar la aplicación de SharePoint](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador SAP](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)