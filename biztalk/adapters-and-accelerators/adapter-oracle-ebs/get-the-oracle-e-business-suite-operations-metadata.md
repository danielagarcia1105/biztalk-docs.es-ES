---
title: Obtener los metadatos de las operaciones de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 566ae086-183a-47db-8f93-12b5903c85c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8904a70d2bfe1b34b28b7cad807796fac752009
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014845"
---
# <a name="get-the-oracle-e-business-suite-operations-metadata"></a>Obtener los metadatos de las operaciones de Oracle E-Business Suite
Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para los artefactos de Oracle E-Business Suite seleccionados. Después de examinar y buscar los artefactos que desea invocar, puede generar el esquema para aquellos artefactos y enviar mensajes, que se ajuste al esquema, para Oracle E-Business Suite.  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes esencialmente la misma interfaz al examinar y buscar las operaciones, por lo que ambos componentes se tratan en los mismos temas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a Oracle E-Business Suite antes de recuperar metadatos para operaciones de destino. Para obtener información sobre cómo conectarse a Oracle base de datos cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in"></a>Generación de esquema mediante el consumir el adaptador de complemento de servicio  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de la categoría, por ejemplo, puede seleccionar la **programas simultáneos** nodo (para generar el esquema para todos los programas simultáneos para una aplicación de Oracle) o puede Seleccione un determinado programa simultáneo. Para obtener más información acerca de los nodos, vea los identificadores de nodo de metadatos.  
  
#### <a name="to-generate-schema-for-oracle-e-business-suite-artifacts"></a>Para generar el esquema para los artefactos de Oracle E-Business Suite  
  
1. Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
   > [!IMPORTANT]
   >  Para generar el esquema para realizar operaciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Debe establecer esta propiedad de enlace al establecer una conexión a Oracle E-Business Suite.  
  
2. Desde el **seleccione el tipo de contrato** lista, seleccione el tipo de contrato en función de si va a generar el esquema para las operaciones de entrada o salidas.  
  
3. Haga clic en el nodo de categoría para el que desea generar los metadatos. Por ejemplo, si desea generar los metadatos para un programa simultáneo dentro de una aplicación de Oracle, haga clic en **programas simultáneos**.  
  
4. Expanda el nodo de categoría y seleccione el elemento específico dentro de ese nodo para el que desea generar los metadatos. Por ejemplo, para generar metadatos para programas simultáneos para la aplicación "Centro de banca", expanda el **programas simultáneos** nodo y, a continuación, haga clic en **banca Center**.  
  
5. En el **operaciones y categorías disponibles** , seleccione las operaciones que se desean invocar y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas aparecen en la **agregar categorías y operaciones** cuadro. Por ejemplo, para invocar "purgar FTP banco" y "Get_Status" de programas simultáneos, haga clic en los nombres de operación y, a continuación, haga clic en **agregar**.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que enumera las operaciones seleccionadas.  
  
    ![Recuperar metadatos de Oracle E&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/df7de132-9177-4de7-a620-59dbd561efe5.gif "df7de132-9177-4de7-a620-59dbd561efe5")  
  
    Si desea generar el esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos "CT1". Después de generar el esquema para "Op1" cerrar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar esquemas para otra operación "Op2". Suponga que "Op2" también contiene un parámetro de tipo de datos "CT1". Después de salir el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, recibirá errores de compilación porque se define el tipo de datos complejos "CT1" dos veces en distintos archivos XSD. En tales situaciones, se recomienda lo siguiente:  
  
   - Genere el esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejos "CT1".  
  
   - Si desea generar el esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar el **generar tipos de esquema únicos** casilla para que los archivos XSD generados contienen espacios de nombres únicos para el "CT1" de tipo de datos complejos.  
  
6. Haga clic en **Aceptar**. El archivo de esquema se guarda con la extensión .xsd en la misma ubicación que el proyecto de BizTalk.  
  
   > [!NOTE]
   >  Si usas el complemento Consume Adapter Service para generar los metadatos para operaciones en los artefactos de Oracle, de forma predeterminada los archivos se crean con una convención de nomenclatura específica: el nombre del archivo XSD generado tiene las siguientes tres partes:  
   > 
   > - "OracleEBSBinding" o el prefijo proporcionado en el **prefijo de nombre de archivo** cuadro.  
   >   - El nombre que se incluye en el **fileNameHint** etiqueta de anotación en el WSDL generado. Para las operaciones, la sugerencia de nombre de archivo es igual que el grupo de la operación. Para los tipos complejos, la sugerencia de nombre de archivo es el espacio de nombres sin el "<http://schemas.microsoft.com/OracleEBS/2008/05/”> prefijo. Por ejemplo, la sugerencia de nombre de archivo para una operación de tabla de interfaz sigue la convención \<InterfaceTables\>+ < app_short_name > + < interface_table_name >.  
   >   - (Opcional) Un entero para asegurarse de que el nombre de archivo es único.  
   > 
   >   Por último, el nombre de un archivo XSD se ha llegado al como < file_name_prefix > +\<fileNameHint\>+ n, donde "n" es un entero único.  
   > 
   > [!NOTE]
   >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace que especificó al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] set de la consola de administración para crear un puerto de WCF-Custom con el URI de conexión, propiedades de enlace y la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
    Metadatos para artefactos de Oracle E-Business Suite se generó correctamente. Puede utilizar los metadatos para enviar mensajes a Oracle E-Business Suite para realizar operaciones específicas. Consulte [aplicaciones de desarrollo de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md) para obtener más información acerca de cómo realizar estas operaciones.  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>Generar un cliente de WCF o contrato de servicio WCF usando la Add Adapter Service Reference complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para las operaciones de salida o código de servicio WCF para las operaciones de entrada.  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-oracle-e-business-suite-operations"></a>Para generar el contrato de servicio o la clase de cliente WCF para las operaciones de Oracle E-Business Suite  
  
1. En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar las operaciones de entrada o salidas.  
  
2. Examine o busque por categorías (por ejemplo, una tabla de interfaz) o para las operaciones específicas para el que desea generar un cliente WCF (o contrato de servicio WCF).   
   Por ejemplo, para buscar las operaciones en la tabla de interfaz AR_ARCHIVE_PURGE_INTERIM, en el **seleccionar una categoría** cuadro:  
  
   1. Expanda el nodo raíz (**/**) para ver las categorías en la que las operaciones se exponen para Oracle E-Business Suite. La misma tabla de la interfaz puede estar disponible en el **vista basada en la aplicación** nodo, así como la **vista basada en el artefacto** nodo. En este ejemplo, genera la clase de cliente WCF desde el **vista basada en la aplicación** nodo.  
  
   2. En el nodo raíz, expanda el **vista basada en la aplicación** nodo para ver las aplicaciones disponibles en Oracle E-Business Suite.  
  
   3. Expanda el nodo de la **cuentas por cobrar** aplicación y, a continuación, expanda el **tablas de interfaz** nodo.  
  
   4. Haga clic en el **AR_ARCHIVE_PURGE_INTERIM** nodo de la tabla de interfaz y en el **operaciones y categorías disponibles** , seleccione las operaciones para el que desea generar un cliente de WCF (o un servicio WCF contrato) y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas aparecen en la **agregar categorías y operaciones** cuadro.  
  
       La siguiente ilustración muestra la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] con las operaciones Insert y Select para la tabla AR_ARCHIVE_PURGE_INTERIM seleccionada.  
  
       ![Generar un contrato de servicio o cliente WCF](../../adapters-and-accelerators/adapter-oracle-ebs/media/oraebs-adap-add-adap-serv-refs.gif "oraebs_adap_add_adap_serv_refs")  
  
      > [!IMPORTANT]
      >  Según las operaciones de salida (o categorías) que usted seleccione, más de un WCF pueden generarse clases de cliente. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
3. Para la mayoría de los escenarios son suficientes; las opciones de serialización predeterminado Sin embargo, si es necesario, puede controlar varios aspectos sobre el código generado y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
   1. Haga clic en **opciones avanzadas** para abrir el **opciones avanzadas** cuadro.  
  
   2. En el **opciones avanzadas** cuadro bajo **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si los métodos asincrónicos se generan para el cliente de WCF o deshabilitar la generación de un archivo de configuración.  
  
   3. En **serializador** selecciona el serializador que se debe usar.  
  
      La siguiente ilustración muestra el **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y ninguna otra opción que se ha seleccionado).  
  
      ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      Las opciones que se pueden configurar en el **opciones avanzadas** cuadro son equivalentes a algunas de las opciones disponibles al utilizar ServiceModel Metadata Utility Tool (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
4. Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda la clase de cliente WCF (o la interfaz de servicio WCF) y código auxiliar para las operaciones y categorías que ha seleccionado en el directorio del proyecto. De forma predeterminada, también se guarda un archivo de configuración. Se generan archivos ligeramente diferentes para las operaciones de entrada y salidas; Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
   Puede seleccionar cualquier nodo que aparece en el **operaciones y categorías disponibles** cuadro. Si selecciona un nodo de categoría, a continuación, se seleccionarán todas las operaciones disponibles en ese nodo y sus nodos secundarios. Por ejemplo, para generar un cliente WCF para todas las operaciones que aparece para la tabla AR_ARCHIVE_PURGE_INTERIM, puede seleccionar la **AR_ARCHIVE_PURGE_INTERIM** nodo.  
  
## <a name="see-also"></a>Vea también  
 [Examinar, buscar y obtener metadatos para operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)