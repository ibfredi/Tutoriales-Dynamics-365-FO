# Extensión de formulario para metodo active del DataSource

[ExtensionOf(formDataSourceStr(EcoResProductDetailsExtended, InventTable))]
internal final class EcoResProductDetailsExtended_FDS_Extension
{
    int active()
    {
        FormDataSource  fds = this;
        InventTable     inventTable;
        int             ret;

        ret = next active();

        inventTable = fds.formRun().dataSource(formDataSourceStr(EcoResProductDetailsExtended, InventTable)).cursor();
        
        // Permite ocultar y bloquear la edición para los campos de Grids de dimensión de producto
        fds.object(fieldNum(InventTable, ItemConfigGridValue_AT)).allowEdit(inventTable.configActive());
        fds.object(fieldNum(InventTable, ItemSizeGridValue_AT)).allowEdit(inventTable.sizeActive());
        fds.object(fieldNum(InventTable, ItemColorGridValue_AT)).allowEdit(inventTable.colorActive());
        fds.object(fieldNum(InventTable, ItemStyleGridValue_AT)).allowEdit(inventTable.styleActive());

        fds.object(fieldNum(InventTable, ItemConfigGridValue_AT)).visible(inventTable.configActive());
        fds.object(fieldNum(InventTable, ItemSizeGridValue_AT)).visible(inventTable.sizeActive());
        fds.object(fieldNum(InventTable, ItemColorGridValue_AT)).visible(inventTable.colorActive());
        fds.object(fieldNum(InventTable, ItemStyleGridValue_AT)).visible(inventTable.styleActive());

        return ret;
    }

}
