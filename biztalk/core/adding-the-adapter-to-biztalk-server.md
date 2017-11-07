---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0491ac0f26b19a96d11cf633263010026961c58b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="adding-the-adapter-to-biztalk-server"></a>Agregar el adaptador a BizTalk Server
El adaptador de BizTalk para JD Edwards OneWorld contiene las carpetas Controlador de recepción y Controlador de envío. La carpeta Controlador de envío contiene BizTalkServerApplication. El adaptador de BizTalk para JD Edwards OneWorld se puede crear; se ejecuta en curso con BizTalk Server y no se ejecuta en un proceso de host aislado.  
  
 Use el procedimiento siguiente para agregar el adaptador a BizTalk Server.  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a>Procedimiento para agregar el adaptador de BizTalk para JD Edwards OneWorld  
  
1.  En el **iniciar** menú, elija **archivos de programa**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server** para iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración.  
  
2.  Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y, a continuación, expanda **configuración de plataforma**.  
  
3.  Haga clic en **adaptadores**, seleccione **New**y haga clic en **adaptador**.  
  
4.  En el **propiedades del adaptador** cuadro de diálogo, escriba un nombre para el adaptador. Por ejemplo, JDEdwards.  
  
5.  Seleccione **JDEOneWorld** desde el **adaptador** lista y, a continuación, haga clic en **Aceptar**.  
  
## <a name="verifying-the-adapter"></a>Verificación del adaptador  
 En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede comprobar que el adaptador funciona correctamente examinando el **sistema lógico** ventana. En la instalación inicial, esta ventana está vacía, porque todavía no se ha establecido ninguna conexión con el sistema de servidor ni se ha creado ningún sistema lógico.  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a>Procedimiento para verificar que el adaptador funciona correctamente  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda **configuración de plataforma**, expanda **adaptadores**y, a continuación, seleccione  **JDEOneWorld**.  
  
2.  En el panel de detalles, haga clic en **BizTalkServerApplication**y seleccione **propiedades**.  
  
3.  Haga clic en la pestaña **Propiedades** .  
  
4.  Establezca los parámetros de la conexión SQL.  
  
    -   **Definir parámetros de la base de datos SQL -** el nombre de SQL Server y la base de datos son los que se establecen durante la instalación. Esta es el área de texto en la que se puede redefinir el servidor y la base de datos del adaptador.  
  
5.  Haga clic en **cerrar** para salir del **sistema lógico** ventana.  
  
     El siguiente paso es agregar un sistema lógico mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Planeamiento y arquitectura](../core/planning-and-architecture17.md)   
 [Seguridad en el adaptador de BizTalk para JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [Agregación del adaptador de BizTalk para JD Edwards OneWorld](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)