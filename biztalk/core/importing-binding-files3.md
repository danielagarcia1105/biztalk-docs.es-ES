---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 5c5cce40f3fbeb580ec7ba854d02cb243e1742b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013467"
---
# <a name="importing-binding-files"></a>Importar archivos de enlace

## <a name="overview"></a>Información general
Antes de utilizar el servidor BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:  
  
-   CLASSPATH apunta a una ubicación específica para los archivos específicos de JD Edwards. Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.  
  
-   Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.  
  
-   Las contraseñas del sistema de JD Edwards, si hay en la configuración se guardan como ***** en el archivo de enlaces. 
  
> [!NOTE]
>  La implementación sobrescribe la configuración de ubicación de recepción. Al implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.  
  
## <a name="import-the-binding-files"></a>Importar archivos de enlace  
  
1.  En el **iniciar** menú, elija **archivos de programa**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server** Para iniciar la consola de administración de BizTalk Server.  
  
2.  Expanda Administración de BizTalk Server, **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Haga clic en la aplicación que desee, seleccione **importación**y, a continuación, haga clic en **enlaces**.  
  
4.  En el **importar enlaces** cuadro de diálogo, busque y seleccione los archivos de enlace y, a continuación, haga clic en **abiertos**.  
  
## <a name="cleaning-the-target-computer"></a>Limpiar el equipo de destino  
Quite los puertos de envío y las ubicaciones de recepción que están enlazados a la orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [Importar JD Edwards OneWorld aplicación](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)