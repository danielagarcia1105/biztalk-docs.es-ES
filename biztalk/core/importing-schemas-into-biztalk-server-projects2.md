---
title: Importar esquemas de JD Edwards EnterpriseOne en Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 640d5884-953a-46b6-b9dc-b931392a3059
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acd61cc8ab63d6859a8e10afb76f93c2f8cb2150
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a>Importación de esquemas en proyectos de BizTalk Server
En este tema se trata la búsqueda de un servidor de JD Edwards EnterpriseOne y la importación de los esquemas a un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Debe asegurarse de que establece el arglist. Debe actualizar jdearglist.txt antes de generar los esquemas en la orquestación. Para obtener más información, consulte [control de valores de cadena](../core/handling-string-values2.md).  
  
> [!NOTE]
>  Cada vez que cambie el jdearglist, debe regenerar los esquemas para ese objeto de negocios.  
  
 Después de crear el puerto de JD Edwards EnterpriseOne, puede explorar JD Edwards EnterpriseOne abriendo el Asistente para adaptador de Microsoft desde un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="import-schemas-into-visual-studio"></a>Importar esquemas en Visual Studio
  
1.  Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  Haga clic en el nombre de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] , seleccione **agregar**y seleccione **agregar elementos generados**.  
  
3.  Haga clic en **agregar** para abrir el **Asistente para agregar adaptador**.  
  
4.  En el **Seleccionar adaptador** , seleccione el nombre del adaptador para el que desea importar esquemas (por ejemplo, **JDEEnterpriseOne**).  
  
5.  En el **SQL Server** , seleccione un servidor SQL server.  
  
6.  En el **base de datos** , seleccione una base de datos.  
  
     La base de datos predeterminada es la misma que el servidor SQL.  
  
7.  En el **puerto** cuadro, seleccione un servidor SQL server y, a continuación, haga clic en **siguiente**.  
  
     El sistema JD Edwards EnterpriseOne se muestra en el explorador.  
  
8.  Continúe con el siguiente procedimiento a continuación.  
  
 El Asistente para agregar adaptador muestra un árbol con todos los sistemas definidos. JD Edwards EnterpriseOne tiene muchos módulos. Los módulos se agrupan juntos de acuerdo con los tres primeros caracteres de su nombre.  
  
-   El primer nivel de la jerarquía es la lista de todos los prefijos de tres caracteres para los nombres de los módulos.  
  
-   El segundo nivel enumera todos los módulos que comparten el mismo prefijo de tres caracteres.  
  
-   El último nivel enumera las funciones empresariales que pertenecen a un módulo. Cuando amplíe el icono de servicios, puede ver sus operaciones.  
  
 Al expandir una operación se muestran los argumentos de entrada y salida. Puede expandir los argumentos de entrada y salida para ver los tipos de datos de los argumentos.  
  
> [!NOTE]
>  Si cambian las definiciones del objeto de servidor, deberá volver a generar el esquema para actualizar los datos que contiene.  
  
> [!NOTE]
>  Si cambia el archivo jdearglist.txt después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene. Para obtener más información sobre jdearglist.txt, consulte [control de valores de cadena](../core/handling-string-values2.md).  
  
## <a name="select-the-schemas"></a>Seleccionar los esquemas  
  
1.  En el **seleccionar servicios para importar** página, expanda el nodo de nivel superior de la **objetos comerciales** nodo o la **servicios empresariales** nodo.  
  
2.  Active la casilla situada junto a los elementos que desea importar y, a continuación, haga clic en **Aceptar**.  
  
3.  Los esquemas generados para los elementos seleccionados de JD Edwards EnterpriseOne se importan en su proyecto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Cuando se utiliza la libreta de direcciones (N0100041) es el nombre del campo **cActionCode**. La acción forma parte del propio archivo XML. Los códigos son:  
  
-   A para Agregar  
  
-   C para Cambiar  
  
-   D para Eliminar  
  
-   I para Consulta  
  
## <a name="next-step"></a>Paso siguiente
[Usar propiedades de contexto de mensaje](../core/using-message-context-properties1.md)