---
title: Publicar extremos SOAP administración de API | Documentos de Microsoft
description: Utilice Feature Pack 1 y Feature Pack 2 para exponer un HTTP de WCF-Basic BizTalk ubicación de recepción como un extremo SOAP en administración de API. Puede hacerlo mediante la consola de administración de BizTalk o pegue el punto de conexión directamente dentro de la API de administración en el portal de Azure.
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
ms.openlocfilehash: eb716729dcdbac07c5b17cf267866cf282046a70
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848956"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a>Publicar extremos de SOAP de BizTalk en administración de API

Exponer los extremos de SOAP de BizTalk como servicios de administración de API de Azure. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, puede exponer un extremo SOAP a través de la API de administración de BizTalk. Puede hacerlo mediante la API de administración en el portal de Azure. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede exponer un WCF-BasicHTTP ubicación de recepción como un punto de conexión en administración de API de Azure mediante la administración de BizTalk. 

> [!TIP]
> [¿Qué es la administración de API? ](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) es un excelente recurso para comprender y obtener más información sobre este servicio de Azure.

## <a name="prerequisites"></a>Requisitos previos
* Configurar y establecer [administración de API de Azure](https://docs.microsoft.com/azure/api-management/api-management-get-started)
* Crear un [red virtual](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) entre el equipo de BizTalk y la instancia de la administración de API
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el servidor BizTalk Server

## <a name="create-using-api-management-in-azure-portal"></a>Crear mediante administración de API en el portal de Azure 
1. En el [portal de Azure](https://portal.azure.com), abra la administración de API y seleccione **API**:

    ![Seleccione la API de BizTalk](../core/media/select-api-for-biztalk.png)
    
2. Seleccione **WSDL**:

    ![Seleccione wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. Configurar las propiedades WSDL: 

    1. **Especificación de WSDL** : escriba el URI completo al extremo SOAP de BizTalk. Por ejemplo, escriba algo parecido a `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` o `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.  

    2. **Paso a través SOAP** o **SOAP al resto** : seleccione sus preferencias: 
        * **SOAP al resto**: crear REST APIs basadas en HTTP desde un servicio web basado en SOAP existente
        * **Paso a través SOAP**: actúa como un proxy para la API de SOAP 

    3. Escriba su preferido **nombre para mostrar**, **nombre**, **descripción**, **sufijo de Url de la API**, **productos**, y **versión**.

    Cuando termine, la configuración de WSDL tiene un aspecto similar al siguiente: 

    ![crear API de BizTalk de WSDL](../core/media/create-api-from-wsdl-biztalk.png)

4. Seleccione **Crear**.

## <a name="create-using-the-biztalk-administration"></a>Crear mediante la administración de BizTalk

> [!NOTE] 
> Esta característica es compatible con WCF-BasicHTTP ubicaciones de recepción. 

1. En la consola de administración de BizTalk, haga el WCF-BasicHTTP ubicación de recepción y seleccione **publicar en administración de API**:  

    ![publicar la opción de menú](../core/media/publish-to-api-management-option.png)
 
2. Configurar las propiedades de administración de API: 

    1. **Inicio de sesión** a su suscripción de Azure, seleccione la **suscripción** y **grupo de recursos** con la administración de API de servicio y, a continuación, seleccione su servicio.

    2. El **vínculo de la especificación de WSDL** se rellena automáticamente con el archivo WSDL. Reemplace **localhost** con el nombre DNS o dirección IP del servidor BizTalk Server. 

    3. Seleccione **paso a través SOAP** o **SOAP al resto**:  
        * **SOAP al resto**: crear REST APIs basadas en HTTP desde un servicios web basados en SOAP existentes
        * **Paso a través SOAP**: actúa como un proxy para la API de SOAP 

        La API se puede publicar ambas formas cambiando el **sufijo de URL de la API**y, a continuación, publicar utilizando un tipo diferente de la API de nuevo.

    4. El **nombre de la API** se rellena automáticamente con el nombre de la ubicación de recepción.

    5. Seleccione un **sufijo de URL de la API** que va a ser utilizado por los consumidores de la API. 

    Cuando termine, las propiedades de aspecto similares al siguiente:  
    ![publicar en la ventana de API](../core/media/api-management-publish-window.png)


3. Seleccione **publicar**. Cuando se realiza correctamente, la ubicación de recepción se muestra como un servicio de administración de API en el [portal de Azure](https://portal.azure.com). 

## <a name="do-more"></a>Llevar a cabo más
Administración de API de Azure es un servicio eficaz que se utiliza una gran cantidad de servicios de Azure, incluidas las aplicaciones de lógica. Administración de API incluye muchas características, incluidos los límites de velocidad y las cuotas, quién tiene acceso a las API, almacenar en caché y mucho más. Vea [¿qué es la administración de API?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) para empezar a trabajar.

## <a name="see-also"></a>Vea también
[Configuración del Feature Pack](configure-the-feature-pack.md)
