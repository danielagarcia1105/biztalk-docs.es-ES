---
title: Probar el servicio web de BizTalk | Documentos de Microsoft
description: "Configurar ubicaciones de recepción y web.config para probar el servicio web de BizTalk en un explorador web"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dc2171d-4abe-43db-b4bc-e484048c6430
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a35373735102bd75d1c388da29b06d4392ba18
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="test-a-biztalk-web-service"></a>Probar un servicio Web de BizTalk

## <a name="overview"></a>Información general
Puede probar el servicio Web publicado sin escribir una aplicación cliente Web. Se puede utilizar un explorador Web, por ejemplo Internet Explorer, para probar el servicio Web publicado. Aunque es posible obtener acceso a cualquier servicio Web publicado mediante un explorador Web, sólo puede probar los servicios Web con métodos Web que contienen parámetros de tipo simple. Para probar el método Web en un explorador Web, los elementos de mensaje para los mensajes de solicitud y respuesta que se usan en el puerto de recepción sólo puede un tipo simple, como **System.String** o **System.Int32**. Si la parte de mensaje utiliza un esquema como tipo de mensaje, no puede probar el método Web con un explorador.  
  
 Si desea probar los servicios Web publicados que usan HTTP-GET o HTTP-POST, debe configurar la ubicación de recepción de BizTalk para el adaptador de SOAP y modificar el archivo Web.config para el servicio Web publicado.  
  
 **Modificar las ubicaciones de recepción**  
  
 Si el adaptador de SOAP configura las ubicaciones de recepción, éste establece normalmente el URI de la ubicación de recepción proporcionando el nombre del archivo .asmx al directorio virtual y al servicio Web:  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 Esto permite al adaptador de SOAP recibir las solicitudes del servicio Web a través del protocolo HTTP-SOAP. Para configurar la ubicación de recepción con el fin de usar el protocolo HTTP-GET o HTTP-POST, debe anexar el nombre del método al URI:  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 El nombre del método es el mismo que el nombre de operación del puerto en la orquestación.  
  
 **Modificar el archivo Web.config**  
  
 De forma predeterminada, el asistente configura los servicios Web para usar el protocolo HTTP-SOAP. HTTP-GET y HTTP-POST se deshabilitan de forma explícita. Para probar un servicio Web con un explorador Web, debe habilitar HTTP-GET.  
  
## <a name="update-the-webconfig"></a>Actualizar el archivo Web.config
  
1.  Abra el archivo Web.config del servicio Web publicado.  
  
    > [!NOTE]
    >  Puede buscar el archivo Web.config en el directorio que ha configurado para la raíz virtual de IIS que contiene el servicio Web.  
  
2.  Buscar el \<protocolos\> sección:  
  
    ```  
    <webServices>  
       <protocols>  
         <remove name="HttpPost" />  
         <remove name="HttpGet" />  
         <remove name="HttpPostLocalhost" />  
       </protocols>  
  
    </webServices>  
    ```  
  
3.  Para probar HTTP-GET, HTTP-POST o HTTP-POST en el equipo local, quite la línea correspondiente de la \<protocolos\> sección.  
  
 Para obtener más información acerca de las opciones de configuración, consulte [opciones de configuración de servicios Web XML creados con ASP.NET](https://msdn.microsoft.com/library/b2c0ew36.aspx). 
  
#### <a name="access-a-web-service-with-internet-explorer"></a>Obtener acceso a un servicio Web con Internet Explorer  
  
-   En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para el servicio Web con el formato  **http://*servername*/*apppath* / *webservicename*.asmx **.  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |***ServerName***|El nombre del servidor en el que ha implementado el servicio Web XML.|  
    |***AppPath***|El nombre del directorio virtual y la ruta de aplicación Web.|  
    |***WebServiceName.asmx***|El nombre del archivo .asmx del servicio Web XML.|  
  
 La descripción del servicio Web muestra todos los métodos del servicio Web que admite el servicio Web concreto. La página de descripción del servicio Web contiene vínculos para los métodos Web disponibles y la descripción del servicio del servicio Web.  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get"></a>Probar un servicio Web con Internet Explorer mediante HTTP-GET  
  
1.  Tras obtener acceso a la página de descripción del servicio Web, haga clic en uno de los métodos Web enumerados en la página de descripción del servicio Web.  
  
2.  Escriba los parámetros necesarios para el método Web y, a continuación, haga clic en **Invoke**.  
  
3.  El servidor devuelve una respuesta XML en el explorador. Si el tipo de datos de retorno del servicio Web es un número de punto flotante de doble precisión, el resultado podría tener el siguiente aspecto:  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a>Probar un servicio Web con Internet Explorer mediante HTTP-GET (método alternativo)  
  
1.  En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para el servicio Web con el formato ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***.  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |***ServerName***|El nombre del servidor en el que ha implementado el servicio Web XML.|  
    |***AppPath***|El nombre del directorio virtual y la ruta de aplicación Web.|  
    |***WebServiceName.asmx***|El nombre del archivo .asmx del servicio Web XML.|  
    |***MethodName***|El nombre de un método público que expone el servicio Web XML. Si se deja en blanco, aparecerá la página de descripción del servicio Web XML, que enumera los métodos públicos disponibles en el archivo .asmx. (Opcional)|  
    |***parámetro***|El nombre y el valor del parámetro correspondiente para los parámetros que requiere el método. Si se deja en blanco, aparecerá la página de descripción del servicio Web XML, que enumera los métodos públicos disponibles en el archivo .asmx. (Opcional)|  
  
    > [!NOTE]
    >  El nombre del método del servicio Web XML con esta sintaxis distingue mayúsculas de minúsculas, pero los nombres del servidor, proyecto y servicio Web XML no hacen esta distinción.  
  
2.  Presione ENTRAR. El explorador Web muestra una respuesta XML en el servidor.  
  
    > [!NOTE]
    >  Además, puede usar HTTP-POST para llamar al servicio Web. Para obtener información y ejemplos sobre cómo llamar a servicios Web XML desde un explorador Web, consulte [acceso a los servicios Web XML desde un explorador](https://msdn.microsoft.com/library/45fez2a8.aspx).  
  
## <a name="see-also"></a>Vea también  
 [Probar servicios web publicados](../core/testing-published-web-services.md)