# grocery_default_value

//For DateTime Value
if( $crud->getState() == 'add' ) { //add these only in add form
    $crud->set_css('assets/grocery_crud/css/ui/simple/'.grocery_CRUD::JQUERY_UI_CSS);
    $crud->set_css('assets/grocery_crud/css/jquery_plugins/jquery.ui.datetime.css');
    $crud->set_css('assets/grocery_crud/css/jquery_plugins/jquery-ui-timepicker-addon.css');
    $crud->set_js('assets/grocery_crud/js/jquery_plugins/jquery-ui-timepicker-addon.js');
    $crud->set_js('assets/grocery_crud/js/jquery_plugins/config/jquery-ui-timepicker-addon.config.js');
}

$crud->callback_add_field('waktu', function () {
    $value = date("d/m/Y H:i:s");
    $return = '<input id="field-waktu" name="waktu" type="text" value="'.$value.'" maxlength="10" class="datetime-input form-control">
                <a class="datetime-input-clear" tabindex="-1" >Clear</a> (dd/mm/yyyy hh:mm:ss)';
    return $return;
});
        
//for Date Value
if( $crud->getState() == 'add' ) { //add these only in add form
    $crud->set_css('assets/grocery_crud/css/ui/simple/'.grocery_CRUD::JQUERY_UI_CSS);
    $crud->set_js('assets/grocery_crud/js/jquery_plugins/config/jquery.datepicker.config.js');
}

$crud->callback_add_field('tgl', function () {
    $value = date("d/m/Y");
    $return = '<input id="field-tgl" name="tgl" type="text" value="'.$value.'" maxlength="10" class="datepicker-input  form-control hasDatepicker">
                <a class="datepicker-input-clear" tabindex="-1" >Clear</a> (dd/mm/yyyy)';
    return $return;
});
