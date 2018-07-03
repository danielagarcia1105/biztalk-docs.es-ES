---
title: Seleccione un esquema de URI y el formato de direcciones cuando se usa el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a9e9ffd78e0740dd366f4f09d3a832e74cda94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005773"
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a>Seleccione un esquema de URI y el formato de direcciones cuando se usa el SDK de adaptador LOB de WCF
Un identificador uniforme de recursos (URI) identifica los recursos como un servicio Web o, en el caso de un adaptador que se desarrollan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], el sistema para conectarse a, así como la acción a realizar. Esta sección proporciona una recomendación sobre cómo construir un URI para describir de forma exclusiva la dirección del extremo y la acción para el adaptador.  
  
## <a name="anatomy-of-a-uri"></a>Anatomía de un URI  
 Un URI consta de los tres componentes siguientes:  
  
- **Nombre de esquema** es la parte responsable de la cadena de URI y es el primer nivel de la estructura de nomenclatura; algunos ejemplos son http, urn y contoso.  
  
- **Parte jerárquica** consta de información que es normalmente jerárquico y puede contener información de puerto, nombre de host y autoridad opcional. Algunos ejemplos son el nombre de usuario y www.microsoft.com =User@microsoft.com:4099.  
  
- **Consulta** contiene la información opcional marcados con un signo de interrogación (?) y normalmente se agrupan como pares clave/valor separados por una y comercial (&). Por ejemplo, contoso://microsoft.com/functions?name=Find.  
  
- **Fragmento** se usa para almacenar información de identificación adicional que puedan ser necesarios para el adaptador. El fragmento se separa mediante un algoritmo hash (#); Por ejemplo, contoso://microsoft.com/functions?name=Find#public.  
  
  No se pueden usar todas las características proporcionadas por la sintaxis de URI.  
  
## <a name="designing-the-uri"></a>Diseñar el URI  
 Como programador de adaptadores, tendrá que idear un URI adecuado para su sistema de línea de negocio de destino. Al diseñar su URI, es importante para que sea único y descriptivo.  
  
 Un URI único es aquel que no entra en conflicto con los URI existentes dentro de una organización y a través de otras empresas e Internet. Por ejemplo, si elige un nombre de esquema, como "http" o "afs" que pueden ser reconocidos actualmente o ya ampliamente usado, pueden producirse problemas operativos o conexión porque se podrían enrutar las solicitudes a un sistema diferente y no a su adaptador.  
  
 Otro aspecto importante del diseño URI es conseguir que sea significativo para la audiencia de desarrolladores que consumen el adaptador. Por ejemplo, si escribe un adaptador para el sistema de procesamiento de notificaciones de un médico, podría diseñar un esquema de URI que incluye el nombre de su compañía, el procesamiento nombre del sistema y la versión del sistema de reclamaciones de destino: northwind.contoso.cps.v1.0://.  
  
## <a name="connecting-to-the-target-system"></a>Conectarse al sistema de destino  
 Las cadenas de conexión tienen la siguiente sintaxis:  
  
 **\<esquema\>: //[userinfo "\@"]\<LOB de la cadena de conexión\>**  
  
 Por ejemplo, podría conectarse al catálogo de contoso (un ejemplo aplicación de línea de negocio) del sistema de pedidos con los siguientes:  
  
 **¿Northwind.contoso.v1.0://\<servername\>? Catálogo = Contoso & Integrated Security = True**  
  
 También puede proporcionar información de la entidad opcional en el URI incluido el nombre de usuario y contraseña y otras credenciales importantes. Sin embargo, esto puede suponer un riesgo de seguridad.  
  
> [!CAUTION]
>  No pase las credenciales de usuario y otra información confidencial en el URI. Esta información se podría interceptar y ver los usuarios no autorizados.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)