<script>
    export default {
        name: 'RowExpand',
        props: ['row', 'columns', 'enable'],
        render(createElement) {
	    if (this.enable) {
                let _slot = this.$parent.expandSlot(this.row);
	    	return createElement('tr', [createElement('td', {attrs: {colspan: this.columns.length}}, _slot)]);
	    } else {
		return '';
	    }
        }
    }    
</script>
