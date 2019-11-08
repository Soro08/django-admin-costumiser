# django-admin-costumiser
Personnaliser la partie admin de django


```bash

list_display = ('',)
list_filter = ('',)

search_fields = ('',)
ordering = ['',]
list_per_page = 20
fields = ['',]
readonly_fields = ['']

filter_horizontal = ('')

list_display_links = ['sku' ,'title',]
date_hierarchy = 'created_at'

inlines = [
    FichierInLine
]

fieldsets = [
        ('Nom', {'fields': ['repectoire', 'role']}),
        

actions = ('active','deactive')
def active(self, request, queryset):
    queryset.update(produit_collections_is_view=False)
    self.message_user(request, 'La selection a été deactivé avec succès')

active.short_description = 'Desactiver'

def deactive(self, request, queryset):
    queryset.update(produit_collections_is_view=True)
    self.message_user(request, 'La selection a été activé avec succès')

deactive.short_description = 'Activer'


def view_image(self, obj):
    return mark_safe('<img src="{url}" width="100px" height="100px" />'.format(url = obj.look_image))




class ModelInLine(admin.TabularInline):
    model = models.Model
    extra = 0

```
