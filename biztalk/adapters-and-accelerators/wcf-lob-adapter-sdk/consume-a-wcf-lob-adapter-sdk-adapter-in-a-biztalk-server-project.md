---
title: Consumir un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: 1b75a3fb19f10188c91120ec816e59996e18c644
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998269"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a>Consumir un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server
Este tema describe cómo consumir un adaptador creado mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] desde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  

> [!NOTE]
>  Para poder usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], debe instalar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] herramientas en el mismo equipo que hospeda [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  


## <a name="use-the-consume-adapter-service-add-in"></a>Use el consumir el adaptador de complemento de servicio  


1. Abra la aplicación de .NET en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  

2. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **proyecto** panel, haga clic en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, elija **agregar**&#124;**agregar elementos generados** &#124;  **Consume Adapter Service**.  

3. En el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] de pantalla, seleccione un enlace del adaptador.  

4. Haga clic en **configurar** para configurar el URI de conexión para el enlace del adaptador seleccionado y para proporcionar las credenciales, propiedades de URI y propiedades de enlace. Los requisitos reales variarán según el enlace del adaptador seleccionado.  

5. Haga clic en **Aceptar** cuando se ha configurado el URI.  

6. Haga clic en **Conectar**. Si el URI de conexión es válida y se aceptan las credenciales del cliente (si existe), el **categoría** panel debe rellenarse con las categorías y las operaciones proporcionadas por el adaptador.  

7. Si el adaptador admite la búsqueda, se activará el campo de búsqueda. En caso contrario, puede filtrar por tipo de contrato y explorar los tipos y las operaciones, haga clic en los nodos en el **categoría** panel.  

8. Haga clic en **Aceptar** para generar los artefactos de proxy. El número de artefactos varía según el tipo de contrato:  


   | Tipo de contrato |  Artefacto   |                         Descripción                         |                                                             |
   |---------------|-------------|-------------------------------------------------------------|-------------------------------------------------------------|
   |   Saliente    | Esquemas XML | Contiene los esquemas para las operaciones y los tipos seleccionados. |                                                             |
   |   Saliente    |             |        XML de información de enlace de puerto de envío WCF-Custom         |  Contiene el XML de configuración para el puerto de envío WCF-Custom.   |
   |    Entrada    | Esquemas XML | Contiene los esquemas para las operaciones y los tipos seleccionados. |                                                             |
   |    Entrada    |             |       XML de información de enlace de puerto de recepción WCF-Custom       | Contiene el XML de configuración de puerto de recepción personalizada de WCF. |


9. Ahora puede usar los archivos de esquema XML en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación.  

## <a name="deploy-the-biztalk-server-project"></a>Implementar el proyecto de BizTalk Server  

1. Abra **administración de BizTalk Server**.  

2. Importe los archivos XML de enlace de puerto para crear los puertos físicos. Haga clic en la aplicación en el **aplicaciones** grupo, seleccione **importar enlaces**y, a continuación, vaya a y seleccione la información de enlace de puerto adecuado archivos XML.  

3. Asigne los puertos lógicos definidos en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orquestaciones para los puertos físicos recién creados.  

4. Haga clic en **orquestaciones** debajo de la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **Enlist**.  

5. Haga clic en **orquestaciones** debajo de la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **iniciar**.  

6. Haga clic en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación y, a continuación, haga clic en **iniciar**.  

## <a name="generate-multiple-schemas"></a>Generar varios esquemas  
 Si usa el Asistente para consumir un servicio adaptador para generar varios esquemas, uno o varios elementos pueden estar duplicados en los esquemas de un error de compilación para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto. Puede evitar esto seleccionando la **genere el tipo de esquema únicos** casilla de verificación para asegurarse de que se generan tipos de esquemas con espacios de nombres únicos.  

## <a name="see-also"></a>Vea también  
 [Consumir un adaptador creado mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)