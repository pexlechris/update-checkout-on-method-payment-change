//# update-checkout-on-method-payment-change
// This hook updates the checkout on method payment change in a woocommerse website
`
<?php
// jQuery - Update checkout on method payment change
add_action( 'wp_footer', 'pexlechris_checkout_jqscript' );
function pexlechris_checkout_jqscript() {
	if ( is_checkout()) :
	?>
	<script type="text/javascript">
	jQuery( function($){
		$('form.checkout').on('change', 'input[name="payment_method"]', function(){
			$(document.body).trigger('update_checkout');
		});
	});
	</script>
	<?php
	endif;
}
`
