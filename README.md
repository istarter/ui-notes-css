# React MUI & Repeated Design CSS

![image](https://github.com/istarter/ui-notes-css/assets/11480617/5478e93a-eaad-44f9-9399-dd8839c63511)

#### Responsive and Scrollabale filters

```javascript
import Dimens from 'assets/dimens';
import { Stack, Box, useTheme } from '@mui/material';
import React from 'react';
import { BodyText } from 'common/presentation/components';

const filters = [
    'All',
    'SOLAR PANELS',
    'Analyzer',
    'Wallbox',
];

const CommunityFilters = () => {
    const theme = useTheme();
    return (
        <Stack
            direction="row"
            spacing={4}
            justifyContent={{ md: 'center' }}
            sx={{
                overflowX: 'scroll',
                '&::-webkit-scrollbar': { display: 'none' },
                scrollbarWidth: 'none',
                msOverflowStyle: 'none',
                minWidth: 0,
            }}
        >
            {filters.map((el) => (
                <Box
                    component="span"
                    sx={{
                        pl: Dimens.BUTTON_PADDING_HORIZONTAL,
                        pr: Dimens.BUTTON_PADDING_HORIZONTAL,
                        border: `1px solid ${theme.palette.success.contrastText}`,
                        borderRadius: '30px',
                        cursor: 'pointer',
                        textAlign: 'center',
                        flexShrink: 0,
                        whiteSpace: 'nowrap',
                    }}
                >
                    <BodyText sx={{
                        fontSize: Dimens.BODY_TEXT_S,
                        fontWeight: Dimens.FONT_WEIGHT_BOLD,
                        color: theme.palette.textMain.main,
                    }}
                    >
                        {el.toUpperCase()}
                    </BodyText>
                </Box>
            ))}
        </Stack>
    );
};

export default CommunityFilters;
