---
title: "Cómo implementar definiciones de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63c3572658e78c7e32722adf38436133ee098e00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-bam-definitions"></a>Cómo implementar definiciones de BAM
Los administradores utilizan el **all implementar** comando de la utilidad de administración de BAM para implementar una definición de BAM desde el libro de Excel o el archivo de definiciones XML exportados desde el libro. Cuando realice una instalación completa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el Asistente para configuración configura automáticamente el XML de configuración de BAM.  
  
> [!NOTE]
>  Si están trabajando varios usuarios con el complemento de BAM para Excel, se recomienda que tengan la misma versión de Microsoft Data Access Components (MDAC). De lo contrario, pueden surgir problemas de compatibilidad. En concreto, si crea una plantilla en un equipo con una versión más reciente de MDAC e intenta abrirla en un equipo que tenga una versión más antigua de MDAC, se producirá un error del compilador.  
  
> [!NOTE]
>  Sólo puede utilizar un elemento de datos (por ejemplo, City) por dimensión de datos (por ejemplo, Location). No puede utilizar City de nuevo en otra dimensión de datos, como Region.  
  
> [!IMPORTANT]
>  Se recomienda comprobar la seguridad de los libros de Excel de BAM (.xls) antes de implementarlos. Se utiliza Excel en el equipo de administración para comprobar la seguridad de los libros de Excel de BAM. Antes de implementar un libro, ábralo y asegúrese de que la seguridad de las macros está establecida en “alta” y que no existen advertencias.  
  
> [!IMPORTANT]
>  En las bases de datos BAM, el "BAM_\<... >" convención de nomenclatura está reservada para todas las entidades SQL (tablas, índices, procedimientos almacenados, funciones, etcetera...). *No* utilizar esta convención de nomenclatura para crear una entidad SQL; este tipo de uso puede dar lugar a un comportamiento indefinido.  
  
 Antes de poder implementar un archivo XML de definición de BAM, debe asegurarse de que la configuración regional que se utiliza para crear este archivo coincide con la configuración regional del equipo en el que lo está implementado. Por ejemplo, si crea un archivo en un equipo que ejecuta la versión en japonés de Microsoft Windows, el equipo en el que implementa el archivo debe estar configurado con la configuración regional en japonés. Si la configuración del equipo y del archivo no coinciden, debe cambiar la configuración del equipo que va a ejecutar la utilidad de administración de BAM por una configuración regional correcta y debe reiniciarlo antes de ejecutar la utilidad.  
  
> [!NOTE]
>  El archivo XML de definición de BAM no puede contener texto en varios idiomas, a no ser que todos los idiomas utilicen la misma página de códigos, o que sólo se incluyan dos idiomas y que uno de ellos sea el inglés.  
  
 Para obtener información acerca de cómo cambiar los parámetros de configuración regional de su equipo, consulte la Ayuda de su sistema operativo.  
  
### <a name="to-deploy-a-bam-definition"></a>Para implementar definiciones de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Navegue hasta la carpeta de seguimiento escribiendo **C:\Program Files\Microsoft BizTalk Server \<versión > \Tracking** en el símbolo del sistema. Presione **ENTRAR**.  
  
3.  Tipo de **bm implementar-all - DefinitionFile:\<archivo de definición de BAM >**.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)