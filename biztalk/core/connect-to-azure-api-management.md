---
title: Publicar puntos de conexión SOAP API Management | Microsoft Docs
description: Utilice Feature Pack 1 y Feature Pack 2 para exponer un HTTP de WCF-Basic BizTalk ubicación de recepción como un extremo SOAP en API management. Puede hacerlo mediante la consola de administración de BizTalk, o pegar el punto de conexión directamente en API Management en Azure portal.
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: 2
author: MandiOhlinger
ms.author: valrobb
manager: anneta
ms.openlocfilehash: c8bdb3cb3f2d0fc247ea607a1b34623006315754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993717"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a>Publicar puntos de conexión de SOAP de BizTalk en API Management

Exponer los extremos de SOAP de BizTalk como servicios en Azure API Management. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, puede exponer un extremo SOAP a través de la API de administración de BizTalk. Puede hacerlo mediante la API de administración en el portal de Azure. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede exponer un WCF-BasicHTTP ubicación de recepción como un punto de conexión en Azure API Management mediante la administración de BizTalk. 

> [!TIP]
> [¿Qué es API Management? ](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) es un excelente recurso para comprender y obtener más información sobre este servicio de Azure.

## <a name="prerequisites"></a>Requisitos previos
* Configurar e instalar [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)
* Crear un [red virtual](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) entre el equipo de BizTalk y la instancia de API Management
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en BizTalk Server

## <a name="create-using-api-management-in-azure-portal"></a>Crear con API Management en Azure portal 
1. En el [portal Azure](https://portal.azure.com), abra la administración de API y seleccione **API**:

    ![Seleccione la API de BizTalk](../core/media/select-api-for-biztalk.png)
    
2. Seleccione **WSDL**:

    ![Seleccione wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. Configure las propiedades de WSDL: 

   1. **Especificación WSDL** : escriba el URI completo a su extremo de SOAP de BizTalk. Por ejemplo, escriba algo parecido a `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` o `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.  

   2. **Paso a través SOAP** o **SOAP a REST** : seleccione la preferencia: 
       * **SOAP a REST**: crear REST APIs basadas en HTTP desde un servicio web basado en SOAP existente
       * **Paso a través SOAP**: actúa como un proxy para la API de SOAP 

   3. Escriba su preferido **nombre para mostrar**, **nombre**, **descripción**, **sufijo Url de API**, **productos**, y **versión**.

      Cuando termine, la configuración de WSDL tiene un aspecto similar al siguiente: 

      ![creación de API de WSDL de BizTalk](../core/media/create-api-from-wsdl-biztalk.png)

4. Seleccione **Crear**.

## <a name="create-using-the-biztalk-administration"></a>Crear mediante la administración de BizTalk

> [!NOTE] 
> Esta característica es compatible con WCF-BasicHTTP las ubicaciones de recepción. 

1. En la consola de administración de BizTalk, haga el WCF-BasicHTTP ubicación de recepción y seleccione **publicar en API Management**:  

    ![opción de menú de publicación](../core/media/publish-to-api-management-option.png)
 
2. Configurar las propiedades de administración de API: 

   1. **Inicio de sesión** a su suscripción de Azure, seleccione el **suscripción** y **grupo de recursos** que tiene la administración de API de servicio y, a continuación, seleccione el servicio.

   2. El **vínculo de especificación WSDL** se rellena automáticamente con el archivo WSDL. Reemplace **localhost** con el nombre DNS o dirección IP del servidor de BizTalk. 

   3. Seleccione **paso a través SOAP** o **SOAP a REST**:  
      * **SOAP a REST**: crear REST APIs basadas en HTTP desde un servicios web basados en SOAP existentes
      * **Paso a través SOAP**: actúa como un proxy para la API de SOAP 

        La API se puede publicar ambas formas cambiando el **sufijo URL de API**y, a continuación, publicar de nuevo con un tipo diferente de la API.

   4. El **nombre de la API** se rellena automáticamente con el nombre de la ubicación de recepción.

   5. Seleccione un **sufijo URL de API** que va a ser utilizado por los consumidores de la API. 

      Cuando termine, las propiedades de aspecto similares al siguiente:  
      ![publicar en la ventana de la API](../core/media/api-management-publish-window.png)


3. Seleccione **publicar**. Cuando se realiza correctamente, se muestra la ubicación de recepción como un servicio de API Management en el [portal Azure](https://portal.azure.com). 

## <a name="do-more"></a>Hacer más cosas
Azure API Management es un servicio eficaz que se usa una buena cantidad de servicios de Azure, incluidas las aplicaciones lógicas. API Management incluye muchas características, incluidos los límites de velocidad y cuotas, quién tiene acceso a las API, almacenamiento en caché y mucho más. Consulte [¿qué es API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) para empezar a trabajar.

## <a name="see-also"></a>Vea también
[Configuración del Feature Pack](configure-the-feature-pack.md)
