---
title: Seleccione un esquema de URI y el formato de direccionamiento al usar el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6df8145fac74761fee4aabd34ff01d708b646c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a>Seleccione un esquema de URI y el formato de direccionamiento al usar el SDK de adaptador LOB de WCF
Un identificador uniforme de recursos (URI) identifica de forma única recursos como un servicio Web o, en el caso de un adaptador que se desarrollan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], el sistema al que conectarse, así como la acción que se va a realizar. Esta sección proporciona una recomendación sobre cómo construir un URI para describir de forma exclusiva la dirección del extremo y la acción para el adaptador.  
  
## <a name="anatomy-of-a-uri"></a>Anatomía de un identificador URI  
 Un URI consta de los tres componentes siguientes:  
  
-   **Nombre de esquema** es la parte inicial de la cadena de URI y es el primer nivel de la estructura de nomenclatura; algunos ejemplos son http, urn y contoso.  
  
-   **Parte jerárquica** consta de información que es normalmente jerárquico y puede contener autoridad opcional, el nombre de host y la información del puerto. Algunos ejemplos son el nombre de usuario y www.microsoft.com =User@microsoft.com:4099.  
  
-   **Consulta** contiene la información opcional marcados con un signo de interrogación (?) y normalmente se agrupan como pares de clave/valor separados por una y comercial (&). Por ejemplo, contoso://microsoft.com/functions?name=Find.  
  
-   **Fragmento** se utiliza para almacenar información de identificación adicional que pueda ser necesaria para el adaptador. El fragmento se separa con una almohadilla (#); Por ejemplo, contoso://microsoft.com/functions?name=Find#public.  
  
 No se pueden usar todas las características proporcionadas por la sintaxis del URI.  
  
## <a name="designing-the-uri"></a>Diseñar el URI  
 Como programador de adaptadores, tendrá que idear un URI adecuado para el sistema de línea de negocio de destino. Al diseñar su URI, es importante para que sea único y descriptivo.  
  
 Un URI único es aquel que no entra en conflicto con URI existentes dentro de una organización y a través de otras empresas e Internet. Por ejemplo, al elegir un nombre de esquema como "http" o "afs" que ya utiliza mucho podría producir conexión o problemas de funcionamiento porque se pueden enrutar las solicitudes a un sistema diferente y no a su adaptador o puede ser reconoce actualmente.  
  
 Otro aspecto importante del diseño URI es conseguir que sea significativo para la audiencia de desarrolladores que usará el adaptador. Por ejemplo, si va a escribir un adaptador para el sistema de procesamiento de notificaciones de un médico, podría diseñar un esquema de URI que incluye el nombre de su compañía, el procesamiento nombre del sistema y la versión del sistema de reclamaciones de destino: northwind.contoso.cps.v1.0://.  
  
## <a name="connecting-to-the-target-system"></a>Conectarse al sistema de destino  
 Cadenas de conexión presentan la sintaxis siguiente:  
  
 **\<esquema >: //[userinfo "@"]\<LOB cadena de conexión >**  
  
 Por ejemplo, puede conectarse al catálogo de contoso (una línea de ejemplo de aplicación de negocio) del sistema de pedidos con los siguientes:  
  
 **¿Northwind.contoso.v1.0://\<servername >? Catálogo = Contoso & Integrated Security = True**  
  
 También puede proporcionar información de la entidad opcional en el URI incluido el nombre de usuario y contraseña y otras credenciales importantes. Sin embargo, esto puede suponer un riesgo de seguridad.  
  
> [!CAUTION]
>  No pase las credenciales de usuario y otra información confidencial en el URI. Esta información se puede interceptar y ver los usuarios no autorizados.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)