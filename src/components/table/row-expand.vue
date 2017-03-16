<script>
    export default {
        name: 'RowExpand',
        props: ['row'],
        computed: {
            owner() {
                let parent = this.$parent;
                while (parent && parent.$options.name !== 'Table') {
                    parent = parent.$parent;
                }
                return parent;
            }
        },
        render(createElement) {
            let _slot = this.owner.$scopedSlots.default ? this.owner.$scopedSlots.default(this.row) : this.owner.$slots.default;
            return createElement('div', _slot);
        }
    }    
</script>
