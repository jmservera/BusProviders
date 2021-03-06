#   R e m o t e   A r d u i n o   P r o v i d e r  
   T h i s   s a m p l e   d e m o n s t r a t e s   h o w   t o   r e p l a c e   t h e   d e f a u l t   b u s   i m p l e m e n t a t i o n s   ( f o r   G P I O ,   I 2 C ,   P W M ,   a n d   A D C )   w i t h   i m p l e m e n t a t i o n s   l e v e r a g i n g   t h e   r e m o t e - w i r i n g   l i b r a r i e s .     T h e s e   l i b r a r i e s   p r o v i d e   a n   e a s y   i n t e r f a c e   f o r   c o n t r o l l i n g   a   r e m o t e   A r d u i n o .  
  
 # #   U s i n g   t h e   A r d u i n o P r o v i d e r s   l i b r a r y   a n d   s a m p l e   c o d e  
 T h i s   s a m p l e   l i b r a r y   p r o v i d e s   a   s e t   o f   W i n d o w s . D e v i c e s . * P r o v i d e r s   W i n R T   A P I s   e n a b l i n g   a p p s   t o   u s e   r e m o t e - w i r i n g ' s   c o m m u n i c a t i o n   w i t h   a n d   c o n t r o l   o f   G P I O ,   I 2 C ,   P W M ,   a n d   A D C   d e v i c e s   o n   a   r e m o t e   A r d u i n o .  
 T h e   c u r r e n t   v e r s i o n   i n c l u d e s :  
 *   A r d u i n o P r o v i d e r s . A r d u i n o P r o v i d e r :   I m p l e m e n t s   I L o w L e v e l D e v i c e s A g g r e g a t e P r o v i d e r   a n d   i s   t h e   t o p   l e v e l   A P I   t o   e n a b l e   r e t r i e v i n g   c o n t r o l l e r   p r o v i d e r s   f o r   G P I O ,   I 2 C ,   P W M ,   a n d   A D C .  
  
 # #   A P I   U s a g e  
 T h e   g e n e r a l   p a t t e r n   o f   t h i s   s a m p l e   p r o v i d e r   ( o r   a n y   o t h e r   W i n R T   c o m p o n e n t   i m p l e m e n t i n g   t h e   W i n d o w s . D e v i c e s . * P r o v i d e r   i n t e r f a c e s )   i s   t o   r e t r i e v e   t h e   t o p   l e v e l   c o n t r o l l e r   f r o m   t h e   p r o v i d e r   a n d   t h e n   u s e   t h e   c o n t r o l l e r   t h e   s a m e   w a y   a s   t h e   d e f a u l t   c o n t r o l l e r s .  
  
 T h e   e a s i e s t   w a y   t o   u s e   t h e s e   p r o v i d e r s   i s   t o   s e t   t h e   A r d u i n o P r o v i d e r   a s   t h e   d e f a u l t   p r o v i d e r   f o r   a n   a p p l i c a t i o n .   T h e   c o d e   b e l o w   w i l l   s e t   i t   a s   t h e   d e f a u l t   p r o v i d e r .    
 ` ` ` C #  
 W i n d o w s . D e v i c e s . L o w L e v e l D e v i c e s C o n t r o l l e r . D e f a u l t P r o v i d e r   =     n e w   A r d u i n o P r o v i d e r s . A r d u i n o P r o v i d e r ( ) ;  
  
 g p i o C o n t r o l l e r   =   a w a i t   G p i o C o n t r o l l e r . G e t D e f a u l t A s y n c ( ) ;  
 i 2 c C o n t r o l l e r   =   a w a i t   I 2 c C o n t r o l l e r . G e t D e f a u l t A s y n c ( ) ;  
 a d c C o n t r o l l e r   =   a w a i t   A d c C o n t r o l l e r . G e t D e f a u l t A s y n c ( ) ;  
 p w m C o n t r o l l e r   =   a w a i t   P w m C o n t r o l l e r . G e t D e f a u l t A s y n c ( ) ;  
 ` ` `  
  
 # #   B u i l d   R e q u i r e m e n t s  
 T h i s   s a m p l e   p r o v i d e r   l i b r a r y   d e p e n d s   o n   t h e   r e m o t e - w i r i n g   c o d e   ( h t t p s : / / g i t h u b . c o m / m s - i o t / r e m o t e - w i r i n g ) .     T o   r u n   t h i s   s a m p l e ,   y o u   w i l l   n e e d   t o :  
  
 1 .   D o w n l o a d   t h e   s a m p l e   c o d e   f o r   t h i s   p r o j e c t   f r o m   g i t h u b   ( h t t p s : / / g i t h u b . c o m / m s - i o t / b u s P r o v i d e r s / a r c h i v e / d e v e l o p . z i p )   a n d   u n z i p   i t   l o c a l l y .     T h e s e   i n s t r u c t i o n s   a s s u m e   y o u   p u t   t h e   c o d e   i n   D : \ b u s P r o v i d e r s - d e v e l o p ,   y o u   m a y   p u t   t h e   c o d e   e l s e w h e r e ,   b u t   a d j u s t   t h e   s u b s e q u e n t   p a t h s   a c c o r d i n g l y .  
 2 .   D o w n l o a d   t h e   r e m o t e - w i r i n g   c o d e   ( h t t p s : / / g i t h u b . c o m / m s - i o t / r e m o t e - w i r i n g / a r c h i v e / d e v e l o p . z i p )   a n d   u n z i p   i t   l o c a l l y .     T h e s e   i n s t r u c t i o n s   a s s u m e   y o u   p u t   t h e   c o d e   i n   D : \ r e m o t e - w i r i n g - d e v e l o p ,   y o u   m a y   p u t   t h e   c o d e   e l s e w h e r e ,   b u t   a d j u s t   t h e   s u b s e q u e n t   p a t h s   a c c o r d i n g l y .  
 3 .   O p e n   t h e   A r d u i n o   s a m p l e   ( D : \ b u s P r o v i d e r s - d e v e l o p \ A r d u i n o \ A r d u i n o C o n s u m e r . s l n ) .     T h e r e   s h o u l d   b e   6   p r o j e c t s :   A r d u i n o C o n s u m e r   ( a   C #   s a m p l e   d e m o n s t r a t i n g   r e m o t e   A r d u i n o   a c c e s s ) ,   A r d u i n o C o n s u m e r C p p   ( a   C + +   s a m p l e   d e m o n s t r a t i n g   r e m o t e   A r d u i n o   a c c e s s ) ,   A r d u i n o P r o v i d e r s   ( a   C + +   p r o j e c t   d e m o n s t r a t i n g   h o w   t o   c r e a t e   a n   a g g r e g a t e   p r o v i d e r   t o   a c c e s s   a n   A r d u i n o   r e m o t e l y ) ,   a n d   t h e   r e m o t e - w i r i n g   p r o j e c t s   ( M i c r o s o f t . M a k e r . F i r a m t a ,   M i c r o s o f t . M a k e r . R e m o t e W i r i n g ,   M i c r o s o f t . M a k e r . S e r i a l ) .  
 4 .   E n s u r e   t h a t   t h e   M i c r o s o f t . M a k e r . F i r m a t a ,   M i c r o s o f t . M a k e r . R e m o t e W i r i n g ,   a n d   M i c r o s o f t . M a k e r . S e r i a l   p r o j e c t s   l o a d   c o r r e c t l y .     T h e   p a t h s   i n   t h e   s o l u t i o n   f i l e s   a r e   r e l a t i v e ,   s o   o u r   s o l u t i o n   a s s u m e s   t h e   s e t u p   d e s c r i b e d   a b o v e .     I f   t h e   M i c r o s o f t . M a k e r . *   p r o j e c t s   a r e   n o t   l o a d e d   c o r r e c t l y   i n   y o u r   s o l u t i o n ,   y o u   c a n   f i x   t h i s   b y   r i g h t - c l i c k i n g   o n   y o u r   A r d u i n o C o n s u m e r   s o l u t i o n ,   s e l e c t i n g   A d d   >   E x i s t i n g   P r o j e c t ,   a n d   s e l e c t i n g   t h e   M i c r o s o f t . M a k e r . *   p r o j e c t s   w h e r e   y o u   d o w n l o a d e d   t h e m .  
 5 .   E n s u r e   t h a t   t h e   A r d u i n o C o n s u m e r ,   A r d u i n o C o n s u m e r C p p   a n d   A r d u i n o P r o v i d e r s   r e f e r e n c e   t h e   M i c r o s o f t . M a k e r . F i r m a t a ,   M i c r o s o f t . M a k e r . R e m o t e W i r i n g ,   a n d   M i c r o s o f t . M a k e r . S e r i a l   p r o j e c t s   c o r r e c t l y .     I f   t h e   M i c r o s o f t . M a k e r . *   r e f e r e n c e s   a r e   n o t   c o r r e c t ,   y o u   c a n   f i x   t h i s   b y   r i g h t - c l i c k i n g   o n   e a c h   A r d u i n o   p r o j e c t ,   s e l e c t i n g   A d d   >   R e f e r e n c e   >   P r o j e c t   >   S o l u t i o n ,   a n d   s e l e c t i n g   t h e   M i c r o s o f t . M a k e r . *   p r o j e c t s .  
 6 .   E n s u r e   t h a t   t h e   W i n d o w s   I o T   E x t e n s i o n s   f o r   t h e   U W P   i s   s e l e c t e d   i n   t h e   R e f e r e n c e s   f o r   t h e   A r d u i n o C o n s u m e r ,   A r d u i n o C o n s u m e r C p p   a n d   A r d u i n o P r o v i d e r s   p r o j e c t s .     I f   i t   i s   n o t ,   y o u   c a n   a d d   i t   b y   r i g h t - c l i c k i n g   o n   e a c h   p r o j e c t ,   c l i c k i n g   A d d   >   R e f e r e r n c e ,   a n d   s e l e c t i n g   U n i v e r s a l   W i n d o w s   >   E x t e n s i o n s   >   W i n d o w s   I o T   E x t e n s i o n s   f o r   t h e   U W P .     Y o u   w i l l   n e e d   a   m i n i m u m   o f   v e r s i o n   1 0 . 0 . 1 0 5 5 6 . 0 .  
 7 .   E n s u r e   t h a t   y o u r   A r d u i n o   i s   c o n f i g u r e d   p r o p e r t l y   f o r   r e m o t e - w i r i n g   ( h t t p s : / / g i t h u b . c o m / m s - i o t / r e m o t e - w i r i n g / b l o b / d e v e l o p / R E A D M E . m d # a r d u i n o - s e t u p ) .  
  
 # #   H a r d w a r e   R e q u i r e m e n t s  
  
 T h e   A r d u i n o C o n s u m e r   a n d   A r d u i n o C o n s u m e r C p p   p r o j e c t s   u t i l i z e   t h e   A D C ,   P W M ,   G P I O ,   a n d   I 2 C   b u s e s   t o   d r i v e   a   " t h e r m o s t a t   d r i v e n   f a n . "     T o   c o n f i g u r e   t h i s ,   y o u ' l l   n e e d   t h e   f o l l o w i n g   h a r d w a r e :  
  
 *   A r d u i n o   b o a r d   ( U N O   i s   u s e d   i n   t h i s   s a m p l e )  
 *   S e r v o   ( d r i v e n   b y   P W M )  
 *   P o t e n t i o m e t e r   ( r e a d   v i a   A D C )  
 *   H T U 2 1 D   t e m p e r a t u r e / h u m i d i t y   s e n s o r   ( r e a d   v i a   I 2 C )  
 *   L E D   ( d r i v e n   b y   G P I O )  
 *   2 2 0   O h m   r e s i s t o r  
 *   P u s h b u t t o n   ( d r i v e n   b y   G P I O )  
 *   1 0 k   O h m   r e s i s t o r  
 *   b r e a d b o a r d   a n d   s o m e   w i r e s  
  
 T o   s e t u p   y o u r   " t h e r m o s t a t   d r i v e n   f a n , "   s e e   h t t p s : / / g i t h u b . c o m / m s - i o t / B u s P r o v i d e r s / b l o b / d e v e l o p / A r d u i n o / A d r u i n o C o n s u m e r _ b b . j p g .  
  
 # # #   S D K   v e r s i o n  
 A d d i t i o n a l l y ,   t h e   f o l l o w i n g   v e r s i o n   o f   t h e   W i n d o w s   S D K   s h o u l d   b e   a v a i l a b l e   f o r   b u i l d i n g   a n d   u s i n g   t h e   l i b r a r y :   1 0 . 0 . 1 0 5 6 3 . 0  
  
 