---
title: "Conectarse a la administración de API de Azure mediante BizTalk Server | Documentos de Microsoft"
description: "Usar BizTalk Feature Pack 1 para conectarse a la administración de API de servidor BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: "2"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d0c5e4cd2a0ebbd7108845ea15de468d0e0a5a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-azure-api-management"></a>Conectarse a la administración de API de Azure
Ahora puede exponer fácilmente su extremo SOAP a través de la API de administración de BizTalk.

## <a name="what-is-azure-api-management"></a>¿Qué es la administración de API de Azure
Use Administración de API de Azure como una solución integrada para la publicación de API a los clientes internos y externos. Crear rápidamente coherente y modernas puertas de enlace de API para los servicios back-end existentes hospedados en cualquier lugar, proteger y protegerlos de abuso y uso excesivo y obtendrá información sobre el uso y estado. Además, automatizar y escalar la incorporación de desarrollador para ayudar a conseguir que un programa API activos y en funcionamiento. 

Vea [administración de API](https://azure.microsoft.com/en-us/services/api-management/) para obtener más información sobre la administración de API.

## <a name="prerequisites"></a>Requisitos previos
* Configurar y establecer [administración de API de Azure](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)
* Crear un [red virtual](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet) entre el equipo de BizTalk y la instancia de la administración de API


1. En el portal de Azure, abra la administración de API y seleccione **API** en el menú:

    ![Seleccione la API de BizTalk](../core/media/select-api-for-biztalk.png)
    
2. Seleccione la opción de **WSDL** en la sección de la nueva API:

    ![Seleccione wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. Para conectarse a la administración de API a su WSDL de BizTalk, copie la dirección URL en el equipo de BizTalk con el URI completo al extremo de SOAP. Por ejemplo, copie `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:

    ![crear API de BizTalk de WSDL](../core/media/create-api-from-wsdl-biztalk.png)

4. Seleccione si desea usar un **paso a través SOAP**, o configuraré un **SOAP al resto** servicio.
5. Escriba el **nombre** de la API, el **descripción**y el **sufijo de Url de la API** para el servicio.
6. Seleccione **crear** para crear la comunicación con su punto de conexión SOAP de back-end.

## <a name="see-also"></a>Vea también
[Configuración del Feature Pack](configure-the-feature-pack.md)