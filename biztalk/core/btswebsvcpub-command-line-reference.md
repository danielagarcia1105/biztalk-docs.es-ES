---
title: Referencia de línea de comandos de BTSWebSvcPub | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62df9b42a9bc709275c836ed2d670d017b217ef6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980445"
---
# <a name="btswebsvcpub-command-line-reference"></a>Referencia de línea de comandos de BTSWebSvcPub
Esta sección proporciona información de referencia para la herramientas de línea de comandos de BTSWebSvcPub incluidas en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede utilizar BTSWebSvcPub para crear servicios Web (.asmx) para publicar orquestaciones mediante los servicios Web como se muestra a continuación:  
  
## <a name="usage"></a>Uso  
 **BTSWebSvcPub PathName [-ubicación:** *valor* **] [-sobrescribir] [-Anonymous]**  
  
 **[-Nombre:** *valor* **] [-Namespace:** *valor* **] [-TargetNamespace:** *valor* **]**  
  
 **[-UnknownHeaders [** *+* **&#124;** *-* **]] [-inicio de sesión único [** *+* **&#124;** *-* **]] [-ParameterStyle:** *valor* **]**  
  
 **[-ConformanceClaims:** *valor* **] [-ForceRequestResponse:** *valor* **] [-ReceiveLocation]**  
  
 **[-ApplicationName:** *valor* **]**  
  
## <a name="parameters"></a>Parámetros  
  
|         Parámetro         | Obligatorio |                                                           Descripción                                                            |
|---------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------|
|       **PathName**        |   Sí    |                    Ruta de acceso y el nombre del ensamblado de BizTalk (\*.dll) o la descripción del servicio web (\*.xml) archivo.                     |
|       **: Ubicación**       |    no    |                                 Ubicación de publicación. (Sintaxis: "http://host[: puerto] / ruta de acceso")                                 |
|      **-Overwrite**       |    no    |                                                  Sobrescribir la ubicación especificada.                                                   |
|      **-Anónimo**       |    no    |                                              Permitir acceso anónimo al servicio Web.                                              |
|         **-Nombre**         |    no    |                    Nombre del ensamblado (archivos .sln y .dll) y de la solución que contiene el servicio Web.                    |
|      **-Namespace**       |    no    |                                             Espacio de nombres predeterminado del código del servicio Web.                                              |
|   **-Targetnamespace**    |    no    |                        Espacio de nombres de destino del servicio Web. (Ejemplo:'<http://www.northwindtraders.com>')                        |
|    **-UnknownHeaders**    |    no    |                                                  Admitir encabezados SOAP desconocidos.                                                   |
|    **-SinglesSignon**     |    no    |                                  Admitir encabezados de inicio de sesión único SOAP de SharePoint Portal Server.                                   |
|    **-ParameterStyle**    |    no    |                               SoapParameterStyle para mensajes: "Default", "Vacío" o "Ajustado".                               |
|  **-ConfirmanceClaims**   |    no    |                              Afirmación de interoperabilidad de servicios Web (WSI): "None" o "Perfilbásico1_1".                              |
| **-ForceRequestResponse** |    no    |                                Exponer operaciones unidireccionales de BizTalk como métodos Web de solicitud-respuesta.                                |
|   **-ReceiveLocation**    |    no    |                                  Cree ubicaciones de recepción en la aplicación de BizTalk especificada.                                  |
|   **-ApplicationName**    |    no    | Nombre de la aplicación de BizTalk en la que se crean ubicaciones de recepción. Si no se especifica, se utiliza la aplicación de BizTalk predeterminada. |
  
## <a name="sample"></a>Ejemplo  
 BTSWebSvcPub.exe "MyAssembly.dll"-ubicación:<http://localhost/MyVdir>  
  
 -Overwrite  
  
## <a name="remarks"></a>Notas  
 Los nombres de parámetros no distinguen entre mayúsculas y minúsculas, y se pueden abreviar. Los valores de parámetros distinguen entre mayúsculas y minúsculas.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como un servicio Web](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)