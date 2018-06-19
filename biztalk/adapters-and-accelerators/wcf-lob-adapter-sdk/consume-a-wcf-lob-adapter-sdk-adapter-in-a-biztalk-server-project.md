---
title: Utilizar un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f81d23b56c2631879f366e6fe502840408a0d7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22225724"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a>Utilizar un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server
Este tema describe cómo consumir un adaptador que se generan con el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
> [!NOTE]
>  Para poder usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], debe instalar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] herramientas en el mismo equipo que hospeda [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 
## <a name="use-the-consume-adapter-service-add-in"></a>Use el Consume Adapter Service complemento  
 
  
1.  Abra la aplicación de .NET en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **proyecto** panel, haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, elija **agregar**&#124;**agregar elementos generados** &#124;  **Consume Adapter Service**.  
  
3.  En el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] pantalla, seleccione un enlace del adaptador.  
  
4.  Haga clic en **configurar** para configurar el URI de conexión para el enlace del adaptador seleccionado y para proporcionar las credenciales, propiedades URI y propiedades de enlace. Los requisitos reales variarán según el enlace del adaptador seleccionado.  
  
5.  Haga clic en **Aceptar** cuando se ha configurado el URI.  
  
6.  Haga clic en **Conectar**. Si el URI de conexión es válida y se aceptan las credenciales del cliente (si existe), el **categoría** panel se debe rellenar con las categorías y las operaciones proporcionadas por el adaptador.  
  
7.  Si el adaptador admite la búsqueda, se activará el campo de búsqueda. En caso contrario, puede filtrar por tipo de contrato y explorar los tipos y las operaciones haciendo clic en los nodos en el **categoría** panel.  
  
8.  Haga clic en **Aceptar** para generar los artefactos de proxy. El número de artefactos varía según el tipo de contrato:  
  
    |Tipo de contrato|Artefacto|Description||  
    |-------------------|--------------|-----------------|-|  
    |Salida|Esquemas XML|Contiene los esquemas para los tipos seleccionados y las operaciones.||  
    |Salida||XML de información de enlace de puerto de envío WCF-Custom|Contiene el XML de configuración para el puerto de envío WCF-Custom.|  
    |Entrada|Esquemas XML|Contiene los esquemas para los tipos seleccionados y las operaciones.||  
    |Entrada||XML de información de enlace de puerto de recepción de WCF-Custom|Contiene el XML de configuración de puerto de recepción de WCF-Custom.|  
  
9. Ahora puede usar los archivos de esquema XML en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación.  
  
## <a name="deploy-the-biztalk-server-project"></a>Implementar el proyecto de BizTalk Server  
  
1.  Abra **administración de BizTalk Server**.  
  
2.  Importe los archivos XML de enlace de puerto para crear los puertos físicos. Haga clic en la aplicación en el **aplicaciones** grupo, seleccione **importar enlaces**y, a continuación, vaya a y seleccione la información de enlace de puerto adecuado archivos XML.  
  
3.  Asigne los puertos lógicos definidos en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orquestaciones a los puertos físicos recién creados.  
  
4.  Haga clic en **orquestaciones** en la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **dar de alta**.  
  
5.  Haga clic en **orquestaciones** en la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **iniciar**.  
  
6.  Haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación y, a continuación, haga clic en **iniciar**.  
  
## <a name="generate-multiple-schemas"></a>Generar varios esquemas  
 Si utiliza el Asistente para consumir un servicio de adaptador para generar varios esquemas, uno o más elementos pueden estar duplicados en los esquemas que se produjo un error de compilación para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto. Para evitarlo, seleccione la **genere el tipo de esquema único** casilla de verificación para asegurarse de que los tipos de esquema se generan con espacios de nombres únicos.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar un adaptador creado mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)